# WLED Projects Collection

A curated collection of WLED presets, configurations, and project ideas for creating stunning LED lighting effects.

## What is WLED?

[WLED](https://kno.wled.ge/) is a fast and feature-rich implementation of an ESP8266/ESP32 webserver to control NeoPixel (WS2812B, WS2811, SK6812) LED strips. It provides:

- Easy-to-use web interface
- Hundreds of built-in effects and palettes
- Mobile app support (iOS & Android)
- Home automation integration (Home Assistant, Alexa, Google Home)
- REST API for custom control
- Real-time control via UDP

## Repository Contents

### 📋 [Presets.md](Presets.md)
A comprehensive collection of 60+ ready-to-use WLED presets organized by theme:
- **Holiday Themes**: Christmas, Halloween, Easter, Valentine's Day, St. Patrick's Day, Thanksgiving, Juneteenth
- **Patriotic**: Red/White/Blue, Patriot variations
- **Seasonal**: Fall Colors, Spring Meadow, Autumn Forest
- **Nature & Atmospheric**: Ocean Breeze, Northern Lights, Starry Night, Desert Sky
- **Effects**: Fireworks, Lightning, Digital Rain, Fireflies
- **Customizable**: Sports Team colors, Accent Lighting

### 📖 [GETTING_STARTED.md](GETTING_STARTED.md)
Step-by-step guide for:
- Setting up your WLED device
- Importing and applying presets
- Creating custom effects
- Troubleshooting common issues

### 💡 [PROJECT_IDEAS.md](PROJECT_IDEAS.md)
Inspiration for your next WLED project with detailed ideas and implementation tips.

## Quick Start

### Applying a Preset

1. **Copy the JSON**: Open [Presets.md](Presets.md) and find your desired effect
2. **Access WLED**: Open your WLED device's web interface (e.g., `http://wled-device.local` or device IP)
3. **Import via API**:
   - Method 1: Use the REST API endpoint: `http://[WLED-IP]/json/state`
   - Method 2: Use WLED app's preset import feature
   - Method 3: Paste directly in browser console

### API Method (Easiest)

```bash
# Replace [WLED-IP] with your device's IP address
curl -X POST http://[WLED-IP]/json/state \
  -H "Content-Type: application/json" \
  -d '{"bri":128,"seg":{"col":[[0,0,255],[8,255,0],[255,0,0]],"fx":84,"sx":128,"ix":128,"pal":0}}'
```

### Browser Console Method

1. Open WLED web interface
2. Press F12 to open Developer Console
3. Paste and modify:
```javascript
fetch('/json/state', {
  method: 'POST',
  headers: {'Content-Type': 'application/json'},
  body: JSON.stringify({"bri":128,"seg":{"col":[[0,0,255],[8,255,0],[255,0,0]],"fx":84,"sx":128,"ix":128,"pal":0}})
});
```

## Understanding Preset Parameters

Each preset JSON contains these key parameters:

| Parameter | Description | Range |
|-----------|-------------|-------|
| `bri` | Brightness | 0-255 |
| `seg` | Segment configuration | Object |
| `col` | Colors (up to 3) | RGB arrays [R,G,B] (0-255) |
| `fx` | Effect ID | 0-180+ (varies by WLED version) |
| `sx` | Effect Speed | 0-255 |
| `ix` | Effect Intensity | 0-255 |
| `pal` | Palette ID | 0-50+ (varies by WLED version) |

### Color Format
```json
"col": [
  [255, 0, 0],    // Primary color (Red)
  [0, 255, 0],    // Secondary color (Green)
  [0, 0, 255]     // Tertiary color (Blue)
]
```

## Customization Tips

### Adjusting Brightness
Change the `bri` value (0-255):
```json
{"bri": 128, ...}  // 50% brightness
{"bri": 255, ...}  // Full brightness
```

### Changing Colors
Modify the RGB values in the `col` array:
```json
"col": [[R, G, B], [R, G, B], [R, G, B]]
```

**Color Examples:**
- Red: `[255, 0, 0]`
- Green: `[0, 255, 0]`
- Blue: `[0, 0, 255]`
- White: `[255, 255, 255]`
- Orange: `[255, 165, 0]`
- Purple: `[128, 0, 128]`

### Speed & Intensity
- Lower `sx` = slower effect
- Higher `sx` = faster effect
- `ix` controls effect intensity/density

## Saving Presets in WLED

1. Apply a preset using the API
2. In WLED web interface, go to **Presets** tab
3. Click **Save preset** and give it a name
4. Now you can recall it with one click!

## Home Automation Integration

### Home Assistant
```yaml
# Example: Trigger Christmas preset
light:
  - platform: wled
    name: Living Room LEDs
    host: 192.168.1.100

automation:
  - alias: "Christmas Lights at Sunset"
    trigger:
      platform: sun
      event: sunset
    action:
      service: rest_command.wled_christmas
```

### Node-RED
Use the HTTP request node to POST presets to your WLED device.

### Alexa/Google Home
WLED supports voice control through Hue emulation or Home Assistant integration.

## Contributing

Have a great preset or project idea? Contributions are welcome!

1. Fork the repository
2. Add your preset to `Presets.md` with a descriptive name
3. Submit a pull request

### Preset Naming Guidelines
- Use descriptive names (e.g., "Ocean Breeze" vs "Effect 1")
- Include theme/category in name when applicable
- Add notes for customizable elements

## Resources

- **Official WLED Documentation**: https://kno.wled.ge/
- **WLED GitHub**: https://github.com/Aircoookie/WLED
- **WLED Discourse Forum**: https://wled.discourse.group/
- **Effect Descriptions**: https://kno.wled.ge/features/effects/
- **API Documentation**: https://kno.wled.ge/interfaces/json-api/
- **WLED App (iOS)**: https://apps.apple.com/app/wled/id1475695033
- **WLED App (Android)**: https://play.google.com/store/apps/details?id=com.aircoookie.WLED

## Hardware Recommendations

### ESP Boards
- **ESP32**: Recommended for complex setups, more memory
- **ESP8266**: Budget-friendly for simple installations
- **ESP32-S2/S3**: Latest generation with improved performance

### LED Strips
- **WS2812B**: Most common, affordable
- **SK6812**: RGBW support (adds white channel)
- **WS2815**: 12V, more resilient to voltage drop

### Power Supplies
- Calculate: ~60mA per LED at full white
- Use 5V for WS2812B/SK6812
- Use 12V for WS2815
- Always size for 80% of max load

## Safety Notes

- Always use proper power supplies rated for your LED count
- Add fuses for fire safety
- Use appropriate wire gauge (lower AWG for longer runs)
- Inject power every 100-150 LEDs on long strips
- Never exceed voltage ratings
- Ensure proper ventilation and heat dissipation

## License

This collection is provided as-is for the WLED community. Feel free to use, modify, and share!

## Support

For WLED software issues, visit the [official WLED GitHub](https://github.com/Aircoookie/WLED/issues).

For questions about these presets, open an issue in this repository.

---

**Happy Lighting! 💡✨**
