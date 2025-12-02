# Getting Started with WLED

This guide will walk you through setting up WLED from scratch and using the presets in this collection.

## Table of Contents
1. [Hardware Setup](#hardware-setup)
2. [Installing WLED](#installing-wled)
3. [Initial Configuration](#initial-configuration)
4. [Using Presets](#using-presets)
5. [Creating Custom Presets](#creating-custom-presets)
6. [Advanced Features](#advanced-features)
7. [Troubleshooting](#troubleshooting)

---

## Hardware Setup

### What You'll Need

**Essential:**
- ESP8266 or ESP32 microcontroller board
- LED strip (WS2812B, SK6812, WS2815, etc.)
- 5V power supply (sized for your LED count)
- USB cable for programming
- Jumper wires

**Recommended:**
- Level shifter (3.3V to 5V) for data line
- 1000µF capacitor across power supply
- 470Ω resistor on data line
- Fuse for safety

### Wiring Diagram

```
Power Supply (+5V) ----[Fuse]----> LED Strip VCC
                    |
                    +-------------> ESP32 VIN (if using 5V board)
                                    or separate 3.3V regulator

Power Supply (GND) --------------> LED Strip GND
                    |
                    +-------------> ESP32 GND

ESP32 GPIO Pin ----[470Ω]--------> LED Strip Data In
   (e.g., GPIO2)

Optional: ESP32 GPIO -----------> LED Strip Clock (for APA102/SK9822)
```

**Important Notes:**
- Connect all grounds together (common ground)
- For long strips (>150 LEDs), inject power every 100-150 LEDs
- Use appropriate wire gauge (18-22 AWG for most projects)
- Add capacitor close to LED strip power input

### Pin Recommendations

**ESP32:**
- Data: GPIO2, GPIO4, GPIO16, GPIO17 (avoid GPIO 6-11, they're used for flash)
- Avoid boot pins: GPIO0, GPIO12, GPIO15

**ESP8266:**
- Data: GPIO2 (D4) recommended
- Alternative: GPIO4 (D2), GPIO5 (D1)

---

## Installing WLED

### Method 1: Web Installer (Easiest)

1. **Visit**: https://install.wled.me/
2. **Connect** your ESP via USB
3. **Click** "Install"
4. **Select** your device from the browser popup
5. **Wait** for installation to complete (2-3 minutes)
6. **Configure** WiFi when prompted

**Browser Requirements:** Chrome, Edge, or Opera (supports Web Serial API)

### Method 2: ESPHome Flasher (Windows/Mac/Linux)

1. **Download** [ESPHome Flasher](https://github.com/esphome/esphome-flasher/releases)
2. **Download** latest WLED binary from [GitHub](https://github.com/Aircoookie/WLED/releases)
   - ESP32: `WLED_[version]_ESP32.bin`
   - ESP8266: `WLED_[version]_ESP8266.bin`
3. **Connect** ESP via USB
4. **Select** Serial Port
5. **Browse** to downloaded .bin file
6. **Click** "Flash ESP"

### Method 3: Arduino IDE (Advanced)

For custom builds with modifications:
1. Install Arduino IDE
2. Add ESP board support
3. Clone WLED repository
4. Configure `platformio.ini` or use Arduino IDE setup
5. Compile and upload

---

## Initial Configuration

### 1. Connect to WLED WiFi

After first boot:
1. Look for WiFi network: `WLED-AP`
2. Connect (default password: `wled1234`)
3. Browser should auto-open to setup page
   - If not, navigate to `http://4.3.2.1`

### 2. Configure WiFi

1. Select your home WiFi network
2. Enter password
3. Click **Save & Connect**
4. Note the IP address shown (or use mDNS: `http://wled.local`)

### 3. LED Configuration

In WLED web interface:
1. Click **Config** → **LED Preferences**
2. Set **LED count** (total number of LEDs)
3. Select **LED type**:
   - WS2812B: Most common RGB strips
   - SK6812: RGBW (includes white channel)
   - WS2815: 12V strips
   - APA102: Clock-based strips
4. Set **Data GPIO** (pin you wired data to)
5. Set **Clock GPIO** (only for APA102/SK9822)
6. Click **Save**

### 4. Test Your Setup

1. Go to main page
2. Move brightness slider
3. Try different effects from dropdown
4. Adjust colors using color picker

If LEDs don't light up, see [Troubleshooting](#troubleshooting).

---

## Using Presets

### Method 1: REST API (Recommended)

**Using cURL (Linux/Mac/Windows PowerShell):**

```bash
# Replace YOUR_WLED_IP with your device IP
curl -X POST http://YOUR_WLED_IP/json/state \
  -H "Content-Type: application/json" \
  -d '{"bri":128,"seg":{"col":[[0,0,255],[8,255,0],[255,0,0]],"fx":84,"sx":128,"ix":128,"pal":0}}'
```

**Using Browser Developer Console:**

1. Open WLED web interface
2. Press **F12** (or **Cmd+Option+I** on Mac)
3. Go to **Console** tab
4. Paste:

```javascript
fetch('/json/state', {
  method: 'POST',
  headers: {'Content-Type': 'application/json'},
  body: JSON.stringify(YOUR_PRESET_JSON_HERE)
});
```

5. Replace `YOUR_PRESET_JSON_HERE` with preset from [Presets.md](Presets.md)
6. Press **Enter**

**Example:**
```javascript
fetch('/json/state', {
  method: 'POST',
  headers: {'Content-Type': 'application/json'},
  body: JSON.stringify({
    "bri": 128,
    "seg": {
      "col": [[255,0,0], [255,255,255], [0,0,255]],
      "fx": 84,
      "sx": 128,
      "ix": 128,
      "pal": 0
    }
  })
});
```

### Method 2: WLED Mobile App

1. **Download** WLED app:
   - [iOS App Store](https://apps.apple.com/app/wled/id1475695033)
   - [Google Play Store](https://play.google.com/store/apps/details?id=com.aircoookie.WLED)

2. **Discover** your device (auto-discovery)
3. **Tap** device to connect
4. Use app interface to control

**To apply presets:**
- Currently, app doesn't have direct JSON import
- Set up presets via web interface first, then recall in app

### Method 3: Save as WLED Preset

Once you've applied a preset via API:

1. Open WLED web interface
2. Click **Presets** button (top right)
3. Click **Save preset**
4. Enter name (e.g., "Christmas Lights")
5. Choose slot number (1-250)
6. Click **Save**

Now you can recall with one click!

**Bonus:** Create preset cycles:
1. Save multiple presets
2. In **Presets** menu, click **Playlist**
3. Add presets to playlist
4. Set duration for each
5. Enable shuffle/cycle options

---

## Creating Custom Presets

### Understanding Effect Parameters

1. **Open Effect Palette**: WLED web interface → Effects dropdown
2. **Experiment** with different effects
3. **Adjust** sliders:
   - Speed (sx): How fast the effect animates
   - Intensity (ix): Effect density/strength
   - Palette: Color scheme for the effect

### Finding Effect IDs

Effects are numbered. To find effect ID:

**Method 1: Check documentation**
- https://kno.wled.ge/features/effects/

**Method 2: Use JSON API**
```bash
curl http://YOUR_WLED_IP/json/state
```
Look for `"fx":` value

**Method 3: Browser console**
```javascript
fetch('/json/state')
  .then(r => r.json())
  .then(d => console.log('Current effect:', d.seg[0].fx));
```

### Export Your Custom Preset

After configuring your perfect look:

1. Open browser console (F12)
2. Run:
```javascript
fetch('/json/state')
  .then(r => r.json())
  .then(d => console.log(JSON.stringify(d, null, 2)));
```
3. Copy the output
4. Save to [Presets.md](Presets.md) or your own file

### Preset Template

```json
{
  "bri": 128,           // Brightness: 0-255
  "seg": {
    "col": [
      [255, 0, 0],      // Primary color (RGB)
      [0, 255, 0],      // Secondary color
      [0, 0, 255]       // Tertiary color
    ],
    "fx": 84,           // Effect ID
    "sx": 128,          // Speed: 0-255
    "ix": 128,          // Intensity: 0-255
    "pal": 0            // Palette ID
  }
}
```

---

## Advanced Features

### Multiple Segments

Split your LED strip into sections:

1. **Config** → **LED Preferences**
2. **Segments** section
3. Define segment ranges:
   - Segment 1: LEDs 0-99
   - Segment 2: LEDs 100-199

Each segment can have different effects!

**API Example:**
```json
{
  "seg": [
    {
      "id": 0,
      "start": 0,
      "stop": 100,
      "col": [[255,0,0],[0,0,0],[0,0,0]],
      "fx": 84
    },
    {
      "id": 1,
      "start": 100,
      "stop": 200,
      "col": [[0,0,255],[0,0,0],[0,0,0]],
      "fx": 46
    }
  ]
}
```

### Time-Based Automation

1. **Config** → **Time & Macros**
2. Enable **NTP Time Sync**
3. Set timezone
4. Create time-based presets:
   - Sunrise: Gentle warm colors
   - Day: Bright white
   - Sunset: Warm orange
   - Night: Dim blue

**Macro Example:**
- Preset 1 at 06:00 (sunrise)
- Preset 2 at 22:00 (bedtime)

### Sync Multiple WLED Devices

**UDP Sync:**
1. **Config** → **Sync Interfaces**
2. Enable **Send UDP** on master device
3. Enable **Receive UDP** on slave devices
4. Use same **Sync group**

Now all devices mirror the master!

**Alternative: MQTT**
- Better for home automation
- Requires MQTT broker (like Mosquitto)

### Button Control

Add physical buttons:
1. **Config** → **LED Preferences** → **Button**
2. Set GPIO pin
3. Choose action:
   - Short press: Next preset
   - Long press: On/Off
   - Double press: Random preset

---

## Troubleshooting

### LEDs Don't Light Up

**Check:**
- [ ] Power supply connected and adequate amperage
- [ ] Correct voltage (5V for WS2812B, 12V for WS2815)
- [ ] Data wire connected to correct GPIO
- [ ] LED count set correctly in WLED
- [ ] Correct LED type selected
- [ ] Strip orientation (data flows one direction)

**Try:**
- Test with single LED first
- Use multimeter to check voltage at LED strip
- Try different GPIO pin
- Add 470Ω resistor on data line
- Add level shifter (3.3V to 5V)

### Wrong Colors

**Possible Causes:**
- Wrong LED type selected (RGB order matters)
- Try different color orders: RGB, GRB, BRG, etc.
- **Config** → **LED Preferences** → **Color Order**

### Flickering or Random Colors

**Causes:**
- Insufficient power supply
- Missing ground connection
- Data line too long without resistor
- Electrical interference

**Solutions:**
- Use thicker power wires
- Add capacitor (1000µF) at power input
- Keep data wire short or use resistor
- Separate power supply for ESP and LEDs

### WiFi Connection Issues

**Can't connect to WLED-AP:**
- Hold button for 5 seconds to reset WiFi
- Power cycle the device
- Check phone WiFi settings (disable mobile data)

**WLED won't connect to home WiFi:**
- Check password (case-sensitive)
- Ensure 2.4GHz network (ESP doesn't support 5GHz)
- Move closer to router during setup
- Check MAC filtering on router

### Preset Doesn't Apply

**Check:**
- Valid JSON syntax (use [JSONLint](https://jsonlint.com/))
- Correct API endpoint: `/json/state`
- WLED version supports effect ID
- Segment exists (default is segment 0)

**Debug:**
```javascript
// Check response
fetch('/json/state', {
  method: 'POST',
  headers: {'Content-Type': 'application/json'},
  body: JSON.stringify(YOUR_PRESET)
})
.then(r => r.json())
.then(d => console.log('Response:', d))
.catch(e => console.error('Error:', e));
```

### Device Keeps Rebooting

**Causes:**
- Power supply insufficient
- Too many LEDs for available memory
- Short circuit
- Corrupted filesystem

**Solutions:**
- Use adequate power supply
- Reduce LED count
- Check wiring for shorts
- Factory reset: Hold button 10+ seconds
- Reflash WLED firmware

### Slow Web Interface

**Causes:**
- Weak WiFi signal
- Too many effects running
- Large LED count

**Solutions:**
- Move device closer to WiFi router
- Disable effects on unused segments
- Use Ethernet (ESP32 with Ethernet adapter)
- Reduce web UI refresh rate

---

## Next Steps

Now that you're set up:

1. Browse [Presets.md](Presets.md) and try different effects
2. Create your own custom presets
3. Check out [PROJECT_IDEAS.md](PROJECT_IDEAS.md) for inspiration
4. Join the [WLED community](https://wled.discourse.group/)
5. Share your creations!

---

## Useful Commands Cheat Sheet

**Get current state:**
```bash
curl http://YOUR_WLED_IP/json/state
```

**Set brightness:**
```bash
curl -X POST http://YOUR_WLED_IP/json/state -d '{"bri":128}'
```

**Turn on/off:**
```bash
curl -X POST http://YOUR_WLED_IP/json/state -d '{"on":true}'
curl -X POST http://YOUR_WLED_IP/json/state -d '{"on":false}'
```

**Set solid color:**
```bash
curl -X POST http://YOUR_WLED_IP/json/state -d '{"seg":{"col":[[255,0,0]]}}'
```

**Load preset by ID:**
```bash
curl -X POST http://YOUR_WLED_IP/json/state -d '{"ps":1}'
```

**Get device info:**
```bash
curl http://YOUR_WLED_IP/json/info
```

---

**Happy Building! 🛠️💡**
