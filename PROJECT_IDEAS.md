# WLED Project Ideas

A collection of creative WLED project ideas, from beginner to advanced, to inspire your next LED installation.

## Table of Contents
- [Beginner Projects](#beginner-projects)
- [Intermediate Projects](#intermediate-projects)
- [Advanced Projects](#advanced-projects)
- [Seasonal & Holiday Projects](#seasonal--holiday-projects)
- [Smart Home Integration](#smart-home-integration)
- [Interactive Projects](#interactive-projects)
- [Outdoor Projects](#outdoor-projects)
- [Art & Decor](#art--decor)
- [Gaming & Entertainment](#gaming--entertainment)
- [Specialized Applications](#specialized-applications)

---

## Beginner Projects

### 1. Under-Cabinet Kitchen Lighting
**Difficulty:** ⭐
**LEDs Needed:** 50-150
**Features:** Solid colors, simple effects

**Implementation:**
- Install LED strip under kitchen cabinets
- Use warm white or tunable white for task lighting
- Add color options for ambiance
- Control via phone app or voice assistant

**Presets to Use:**
- AccentLighting1, AccentLighting2 (task lighting)
- Custom warm white for cooking
- Color options for parties

---

### 2. Desktop Mood Lighting
**Difficulty:** ⭐
**LEDs Needed:** 30-100
**Features:** Color cycling, music reactive

**Implementation:**
- Line back edge of desk or monitor
- USB-powered for convenience
- Sync with computer activities
- Gentle effects for focus, vibrant for gaming

**Presets to Use:**
- Zen Garden (focus mode)
- RGB (gaming mode)
- Moonlight Clarity (late night work)

---

### 3. Bedroom Accent Strip
**Difficulty:** ⭐
**LEDs Needed:** 50-200
**Features:** Gentle effects, wake-up simulation

**Implementation:**
- Install behind headboard or along ceiling
- Warm colors for evening wind-down
- Sunrise simulation for natural wake-up
- Night light mode (low brightness red/orange)

**Presets to Use:**
- Sunset (evening)
- Sunrise (morning alarm)
- Valentines Day (romantic mode)

---

### 4. Stairs Lighting
**Difficulty:** ⭐⭐
**LEDs Needed:** 50-200 (depending on stairs)
**Features:** Safety lighting, motion activated

**Implementation:**
- Install strip under each step's edge
- Add PIR motion sensor for auto-on
- Gentle upward color flow when activated
- Low brightness white for safety

**Presets to Use:**
- Custom white for safety
- Galactic Train (colorful ascent effect)
- Northern Lights (decorative mode)

---

## Intermediate Projects

### 5. Infinity Mirror
**Difficulty:** ⭐⭐⭐
**LEDs Needed:** 60-144
**Features:** Symmetrical effects, mesmerizing patterns

**Materials:**
- Two-way mirror glass
- Regular mirror
- Frame (shadow box or custom)
- LED strip (addressable)

**Implementation:**
- Create frame with mirrors facing each other
- Install LEDs around inner perimeter
- Spacing creates infinite tunnel effect
- Best with radial/circular effects

**Presets to Use:**
- Digital Rain (cascading tunnel)
- Cosmic Nebula (space portal)
- FireworksBlue (explosive effect)

---

### 6. Smart Closet Lighting
**Difficulty:** ⭐⭐
**LEDs Needed:** 50-150
**Features:** Auto-on with door, CRI lighting

**Implementation:**
- Install strips on closet sides/top
- Add door sensor for automation
- High CRI white for true color matching
- Gentle fade in/out

**Hardware:**
- Door contact sensor (magnetic)
- ESP with deep sleep (battery powered option)

**Code Addition:**
- Wake on door open
- Auto-off after 5 minutes

---

### 7. PC Case RGB Lighting
**Difficulty:** ⭐⭐
**LEDs Needed:** 30-100
**Features:** Sync with PC status, temperature reactive

**Implementation:**
- Install inside PC case (around edges, behind GPU)
- USB power from motherboard
- Sync with system metrics via API
- Different colors for temperature ranges

**Integration:**
- Use Python script to read CPU/GPU temps
- POST color changes to WLED
- Blue (cool) → Green (warm) → Red (hot)

**Advanced:**
- Sync with game events
- Audio reactive for music/games

---

### 8. Bookshelf Backlighting
**Difficulty:** ⭐⭐
**LEDs Needed:** 100-300
**Features:** Per-shelf control, reading light

**Implementation:**
- Strip behind each shelf
- Separate segments for each level
- Adjustable brightness per section
- Warm white for reading

**Presets to Use:**
- Custom warm white segments
- Forest Magic (ambient green)
- Enchanted Garden (magical library feel)

---

### 9. Outdoor Patio Lighting
**Difficulty:** ⭐⭐⭐
**LEDs Needed:** 200-500
**Features:** Weatherproof, colorful ambiance

**Implementation:**
- Use IP65+ rated LED strips
- Weatherproof enclosure for ESP32
- Install under railings or eaves
- Create zones for different areas

**Important:**
- Weatherproof power supplies
- Sealed connectors
- Drip loops for wiring

**Presets to Use:**
- Ocean Breeze (relaxing)
- Sunset (evening gatherings)
- Fireflies (romantic dinners)

---

### 10. Workshop/Garage Task Lighting
**Difficulty:** ⭐⭐
**LEDs Needed:** 200-500
**Features:** Bright work light, zone control

**Implementation:**
- High-density LED strips overhead
- Multiple segments for different work areas
- Bright white for detailed work
- Color zones for organization

**Presets to Use:**
- Full brightness white (work mode)
- Custom colors for different zones
- Red (tool area), Blue (paint area), etc.

---

## Advanced Projects

### 11. LED Matrix Display
**Difficulty:** ⭐⭐⭐⭐
**LEDs Needed:** 256-1024 (16x16 to 32x32)
**Features:** 2D effects, text scrolling, animations

**Implementation:**
- Create grid of LED strips
- Use WLED 2D support (0.14.0+)
- Display patterns, text, images
- Game of Life, Matrix rain, etc.

**Configuration:**
- Enable 2D in WLED settings
- Define matrix dimensions
- Test with 2D effects

**Applications:**
- Wall art
- Information display
- Visual notifications
- Retro gaming displays

---

### 12. Ambilight TV Backlight
**Difficulty:** ⭐⭐⭐⭐
**LEDs Needed:** 100-300
**Features:** Screen color sync, immersive viewing

**Implementation:**
- Install LEDs around TV perimeter
- Use Hyperion or Prismatik software
- Capture screen colors
- Send to WLED in real-time

**Software Setup:**
1. Install Hyperion on Raspberry Pi or PC
2. Configure capture device (HDMI splitter or screen capture)
3. Map LED positions to screen areas
4. Configure WLED as output device

**Alternative:** Use HyperHDR for HDR support

---

### 13. Music Visualizer Stand-Alone System
**Difficulty:** ⭐⭐⭐⭐
**LEDs Needed:** 144-300
**Features:** FFT analysis, bass/mid/treble reactive

**Hardware:**
- ESP32 (required for processing power)
- INMP441 I2S microphone
- LED strip

**Implementation:**
- Connect microphone to ESP32
- Use WLED sound reactive fork or SR-WLED
- FFT analysis for frequency separation
- Different effects react to different frequencies

**Effects:**
- Bass = bottom LEDs pulse
- Mids = center color changes
- Treble = top sparkles

**Resources:**
- Sound Reactive WLED: https://github.com/atuline/WLED

---

### 14. Synchronized Multi-Room Lighting
**Difficulty:** ⭐⭐⭐
**LEDs Needed:** Variable
**Features:** Whole-home color themes, scenes

**Implementation:**
- Install WLED in multiple rooms
- Use UDP sync or MQTT
- Create house-wide themes
- Time-based automation

**Scenes:**
- Morning: Gentle warm sunrise (all rooms)
- Day: Bright, productive whites
- Evening: Warm, relaxing colors
- Night: Low red/orange for sleep
- Party: Synchronized colorful effects

**Home Assistant Integration:**
```yaml
scene:
  - name: "Movie Night"
    entities:
      light.living_room_leds:
        state: on
        brightness: 30
        rgb_color: [148, 0, 211]
      light.hallway_leds:
        state: on
        brightness: 10
        rgb_color: [148, 0, 211]
```

---

### 15. Weather Reactive Display
**Difficulty:** ⭐⭐⭐⭐
**LEDs Needed:** 100-300
**Features:** Current conditions visualization

**Implementation:**
- Fetch weather API data
- Map conditions to colors/effects
- Update WLED automatically

**Color Mapping:**
- Sunny: Bright yellow/orange
- Cloudy: Gray/white
- Rainy: Blue with drip effect
- Stormy: Purple/white lightning effect
- Snowy: White/blue gentle sparkle

**APIs to Use:**
- OpenWeatherMap
- Weather.gov
- Dark Sky (if grandfathered)

**Platform:**
- Node-RED flow
- Python script on Raspberry Pi
- Home Assistant automation

---

## Seasonal & Holiday Projects

### 16. Animated Halloween Decorations
**Difficulty:** ⭐⭐
**LEDs Needed:** Variable
**Features:** Spooky effects, motion triggered

**Ideas:**
- Pumpkin eyes with flickering
- Window silhouette backlighting
- Pathway markers (orange/purple)
- Spider web illumination

**Presets to Use:**
- Halloween
- Witching Hour
- Lightning (thunderstorm effect)

**Motion Integration:**
- PIR sensor triggers scary effect
- Return to ambient after timeout

---

### 17. Christmas Light Display
**Difficulty:** ⭐⭐⭐
**LEDs Needed:** 500-2000+
**Features:** Synchronized music, patterns

**Implementation:**
- Outline house features
- Use multiple controllers
- Sync via UDP/MQTT
- Create choreographed sequences

**Presets to Use:**
- Christmas, Christmas2, Christmas3, Christmas4
- ChristmasZzs
- Fireworks (for finale)

**Advanced:**
- Sync to music using xLights software
- Create custom sequences
- DMX control for integration

---

### 18. Easter Egg Hunt Markers
**Difficulty:** ⭐
**LEDs Needed:** 50-100 per marker
**Features:** Colorful, waterproof

**Implementation:**
- LED strips in clear tubes/stakes
- Battery powered (rechargeable)
- Pastel colors for egg locations
- Remote control to enable/disable zones

**Presets to Use:**
- Easter Stubs
- Spring Meadow
- Custom pastel colors

---

### 19. Independence Day Patriotic Display
**Difficulty:** ⭐⭐
**LEDs Needed:** 200-1000
**Features:** Red/white/blue effects

**Implementation:**
- House outline or flag display
- Firework simulation effects
- Sequenced patriotic patterns

**Presets to Use:**
- Patriot, Patriot2
- Red White Blue
- Fireworks, FireworksRed, FireworksBlue

---

## Smart Home Integration

### 20. Voice-Controlled Lighting
**Difficulty:** ⭐⭐
**Features:** Alexa, Google Home, Siri

**Alexa Setup:**
- Enable Hue emulation in WLED
- Discover devices in Alexa app
- Create routines for scenes

**Google Home:**
- Add WLED via Home Assistant
- Use MQTT or REST integration
- Voice commands for presets

**Siri/HomeKit:**
- Use Homebridge plugin
- Add as accessory
- Create scenes and automations

---

### 21. Presence-Based Automation
**Difficulty:** ⭐⭐⭐
**Features:** Auto-adjust based on occupancy

**Implementation:**
- Use phone presence detection
- Motion sensors in rooms
- Time-based rules

**Home Assistant Example:**
```yaml
automation:
  - alias: "Welcome Home Lights"
    trigger:
      platform: state
      entity_id: person.user
      to: 'home'
    condition:
      condition: sun
      after: sunset
    action:
      service: light.turn_on
      entity_id: light.entry_leds
      data:
        brightness: 200
        rgb_color: [255, 200, 100]
```

---

### 22. Sleep Tracking Integration
**Difficulty:** ⭐⭐⭐
**Features:** Sync with sleep apps

**Implementation:**
- Connect to sleep tracker API
- Dim lights when sleep detected
- Gradual wake-up simulation
- Red/amber only during sleep

**Compatible Services:**
- Sleep as Android
- Sleep Cycle
- Withings Sleep
- Apple Health

---

## Interactive Projects

### 23. Button/Touch Control Panel
**Difficulty:** ⭐⭐⭐
**LEDs Needed:** Variable
**Features:** Physical preset selection

**Hardware:**
- ESP32
- Capacitive touch sensors or buttons
- Optional: Small OLED display

**Implementation:**
- Each button = different preset
- Hold button = brightness adjust
- Display shows current preset name

**Button Functions:**
- Button 1: Warm white
- Button 2: Cool white
- Button 3: Color cycle
- Button 4: Movie mode
- Button 5: Party mode

---

### 24. Gesture Control
**Difficulty:** ⭐⭐⭐⭐
**LEDs Needed:** Variable
**Features:** Touchless control

**Hardware:**
- APDS-9960 gesture sensor
- ESP32

**Gestures:**
- Swipe up: Brightness increase
- Swipe down: Brightness decrease
- Swipe left: Previous preset
- Swipe right: Next preset
- Near proximity: On/off toggle

**Code:**
- Read gesture sensor
- Map to WLED API calls
- Implement cooldown to prevent accidental triggers

---

### 25. NFC Tag Preset Switching
**Difficulty:** ⭐⭐⭐
**LEDs Needed:** Variable
**Features:** Tap to change scenes

**Hardware:**
- PN532 NFC reader
- NFC tags (stickers or cards)

**Implementation:**
- Each NFC tag = unique preset
- Tap card near reader
- WLED switches to assigned preset

**Use Cases:**
- Guest card: Party colors
- Sleep card: Night mode
- Work card: Focus lighting
- Movie card: Theater mode

---

### 26. Distance/Proximity Reactive
**Difficulty:** ⭐⭐⭐
**LEDs Needed:** 100-300
**Features:** Changes based on proximity

**Hardware:**
- Ultrasonic sensor (HC-SR04)
- ESP32

**Implementation:**
- Measure distance to nearest object
- Map distance to color/brightness
- Near = bright/warm, Far = dim/cool

**Applications:**
- Interactive art installation
- Retail display
- Museum exhibit
- Welcome mat (brighten as you approach)

---

## Outdoor Projects

### 27. Garden Pathway Lights
**Difficulty:** ⭐⭐
**LEDs Needed:** 50-100 per stake
**Features:** Solar or wired, weatherproof

**Implementation:**
- Create LED stakes for pathway
- IP67 LED strips
- Weatherproof enclosures
- Warm white or color changing

**Power Options:**
- Solar panels with batteries
- Low-voltage wired system
- Automatic dusk-to-dawn

---

### 28. Pool/Pond Lighting
**Difficulty:** ⭐⭐⭐
**LEDs Needed:** 200-500
**Features:** Fully waterproof (IP68)

**Safety First:**
- Use low voltage (12V)
- Proper IP68 rated strips
- GFCI protected circuits
- Professional install if unsure

**Implementation:**
- Submersible LED strips
- Underwater color effects
- Timer-based automation

**Presets to Use:**
- Ocean Breeze
- Deep Sea
- Aurora Dreams

**Important:** Follow local electrical codes for water features.

---

### 29. Deck/Pergola Accent Lighting
**Difficulty:** ⭐⭐
**LEDs Needed:** 300-1000
**Features:** Weatherproof, dimmable

**Implementation:**
- Outline deck perimeter
- Under railing illumination
- Pergola beam highlights
- Create zones for different areas

**Presets to Use:**
- Sunset (evening ambiance)
- Fireflies (romantic)
- Custom white (task lighting)

---

### 30. House Outline/Architectural Lighting
**Difficulty:** ⭐⭐⭐
**LEDs Needed:** 1000-5000+
**Features:** Permanent installation

**Implementation:**
- Outline roof lines, columns, windows
- Use aluminum channels for clean look
- Multiple controllers for large installations
- Synchronize via UDP

**Permanent Install Tips:**
- Use UV-resistant materials
- Aluminum channels protect LEDs
- Plan power injection points
- Consider accessibility for maintenance

---

## Art & Decor

### 31. LED Wall Art
**Difficulty:** ⭐⭐⭐
**LEDs Needed:** Variable
**Features:** Custom designs, patterns

**Ideas:**
- Mountain range silhouette with sunrise
- Geometric patterns
- Wave/ocean scene
- Constellation map

**Implementation:**
- Design shape (wood, acrylic, 3D print)
- Install LEDs in pattern
- Diffuser for glow effect
- Frame/mount on wall

---

### 32. Floating Shelf Illumination
**Difficulty:** ⭐⭐
**LEDs Needed:** 30-60 per shelf
**Features:** Indirect lighting, modern aesthetic

**Implementation:**
- Install LEDs on back top edge of shelf
- Light reflects off wall
- Floating glow effect
- Highlight displayed items

**Tip:** Use warm white for classic look, RGB for modern

---

### 33. Picture Frame Backlighting
**Difficulty:** ⭐
**LEDs Needed:** 20-50 per frame
**Features:** Highlight artwork

**Implementation:**
- Install strip around frame back
- ~1-2 inch gap from wall
- Creates halo effect
- Adjustable colors to complement art

---

### 34. Neon Sign Replica
**Difficulty:** ⭐⭐⭐
**LEDs Needed:** Variable
**Features:** Custom text/shapes

**Materials:**
- Flexible LED neon rope or dense strip
- 3D printed mounting brackets
- Acrylic or wood backing

**Implementation:**
- Design text/shape in CAD
- 3D print mounting points
- Route LED neon through mounts
- Mount to board

**Advantages over real neon:**
- Much safer (low voltage)
- Changeable colors
- Less fragile
- Lower power consumption

---

## Gaming & Entertainment

### 35. Gaming Setup RGB
**Difficulty:** ⭐⭐
**LEDs Needed:** 100-300
**Features:** Sync with games, reactive

**Implementation:**
- Desk background lighting
- Monitor backlighting
- Sync with in-game events via API

**Integrations:**
- Razer Chroma (if compatible)
- Philips Hue sync (via bridge emulation)
- Custom game-specific scripts

**Examples:**
- Health bar: Green → Yellow → Red
- Ammo count: Flashing when low
- Team colors in multiplayer

---

### 36. Home Theater Lighting
**Difficulty:** ⭐⭐
**LEDs Needed:** 200-500
**Features:** Movie mode, automated dimming

**Implementation:**
- Wall wash lighting
- Step lighting for safety
- Automated dimming when movie starts

**Home Automation:**
```yaml
automation:
  - alias: "Movie Mode"
    trigger:
      platform: state
      entity_id: media_player.tv
      to: 'playing'
    action:
      service: light.turn_on
      entity_id: light.theater_leds
      data:
        brightness: 5
        rgb_color: [50, 0, 80]
```

---

### 37. Arcade Cabinet Lighting
**Difficulty:** ⭐⭐⭐
**LEDs Needed:** 100-300
**Features:** Retro aesthetic, game-reactive

**Implementation:**
- Marquee backlighting
- Control panel edge lighting
- Coin door illumination
- Sync to game events

**RetroPie Integration:**
- Script to detect game launch
- Change colors per console/game
- NES = Red, SNES = Purple, Genesis = Blue

---

### 38. Streaming Studio Lights
**Difficulty:** ⭐⭐
**LEDs Needed:** 200-500
**Features:** Key lighting, scene presets

**Implementation:**
- Background accent lighting
- Edge lighting for depth
- Preset scenes for different streams

**Scenes:**
- Gaming: Vibrant colors
- Chatting: Soft warm white
- Starting Soon: Slow color cycle
- Be Right Back: Dim blue
- Alert: Bright flash (subs/donations)

**Integration:**
- StreamerBot
- OBS websocket
- Streamlabs alerts

---

## Specialized Applications

### 39. Aquarium Lighting
**Difficulty:** ⭐⭐⭐
**LEDs Needed:** Variable
**Features:** Spectrum control, day/night cycle

**Important:**
- Use aquarium-safe materials
- Correct spectrum for plants/coral
- Avoid overheating water

**Implementation:**
- Mount above tank (not submerged unless rated)
- Adjustable white balance
- Dawn/dusk simulation
- Moonlight mode at night

**Spectrum:**
- Freshwater plants: 6500K white
- Saltwater coral: Blue-heavy spectrum
- Fish-only: Any color

---

### 40. Plant Grow Lights
**Difficulty:** ⭐⭐
**LEDs Needed:** Variable
**Features:** Full spectrum, timer

**Note:** WLED RGB strips are NOT optimal for plant growth. Consider:
- Adding separate grow light spectrum LEDs
- Or use this as supplemental/aesthetic lighting

**Implementation:**
- Supplement with red/blue grow lights
- WLED for aesthetic purple glow
- Timer for 12-16 hour photoperiod

---

### 41. Photography/Video Lighting
**Difficulty:** ⭐⭐⭐
**LEDs Needed:** 300-1000
**Features:** High CRI, adjustable color temp

**Requirements:**
- High CRI (>90) LED strips
- Diffusion for even lighting
- Adjustable brightness and color temp

**DIY Light Panel:**
- Mount LEDs on board
- Add diffusion material (frosted acrylic)
- Use warm white + cool white strips
- Mix to achieve desired color temp (3000K-6500K)

**WLED Control:**
- Adjust brightness per scene
- Save presets for different setups

---

### 42. 3D Printer Enclosure Lighting
**Difficulty:** ⭐⭐
**LEDs Needed:** 50-150
**Features:** Bright white, visibility

**Implementation:**
- Install inside enclosure
- Bright white for print monitoring
- Optional: Red mode for heat-sensitive materials
- Automatic on when printing

**Integration:**
- OctoPrint plugin
- Turn on lights when print starts
- Celebrations rainbow when print completes

---

### 43. Sign/Logo Illumination (Business)
**Difficulty:** ⭐⭐⭐
**LEDs Needed:** Variable
**Features:** Brand colors, scheduling

**Implementation:**
- Backlight business sign
- Set brand colors as default
- Schedule: On during business hours
- Special effects for promotions

**Features:**
- Holiday themes
- Sale announcements (flashing/bright)
- Closed: Dim or off

---

### 44. Vehicle Interior Lighting
**Difficulty:** ⭐⭐
**LEDs Needed:** 100-300
**Features:** 12V compatible, mobile control

**Important:**
- Check local laws (some colors illegal while driving)
- Don't obstruct driver vision
- Use automotive-rated components

**Implementation:**
- Under-dash footwell lighting
- Door panel accents
- Trunk lighting
- WLED powered by 12V car battery
- WiFi hotspot from phone for control

**Safety:**
- Avoid bright/flashing while driving
- Use warm dim colors if any lights visible to driver

---

### 45. Server Rack Status Indicators
**Difficulty:** ⭐⭐⭐
**LEDs Needed:** 100-300
**Features:** Status visualization

**Implementation:**
- LED strip in rack
- Segment per server
- Color = status

**Status Mapping:**
- Green: Online, healthy
- Blue: High load
- Yellow: Warning (high temp, disk space)
- Red: Critical/offline
- Purple: Maintenance mode

**Integration:**
- Python script monitors servers
- API calls to WLED
- SNMP, SSH, or agent-based monitoring

---

## Advanced Automation Ideas

### 46. AI-Powered Mood Lighting
**Difficulty:** ⭐⭐⭐⭐
**Features:** Learns preferences, auto-adjusts

**Implementation:**
- Track when user manually changes lights
- Log time, weather, activity
- Use machine learning to predict preferences
- Auto-suggest scenes

**Tools:**
- Home Assistant + ML integration
- Node-RED with ML nodes
- Custom Python ML model

---

### 47. Calendar-Based Event Lighting
**Difficulty:** ⭐⭐⭐
**Features:** Syncs with calendar

**Implementation:**
- Read calendar API (Google, Outlook)
- Event types trigger scenes
- "Meeting": Focus white
- "Lunch": Warm casual
- "Exercise": Energizing blue
- "Sleep": Night mode

---

### 48. Air Quality Reactive
**Difficulty:** ⭐⭐⭐
**Features:** Visual air quality indicator

**Hardware:**
- Air quality sensor (BME680, CCS811)
- ESP32

**Implementation:**
- Monitor CO2, VOC, particulates
- Map to color gradient
- Green (good) → Yellow (moderate) → Red (poor)

---

### 49. Stock Market Tracker
**Difficulty:** ⭐⭐⭐
**Features:** Visual market indicator

**Implementation:**
- Fetch stock prices via API
- Up day: Green effects
- Down day: Red effects
- Intensity = percent change

**APIs:**
- Alpha Vantage
- Yahoo Finance
- IEX Cloud

---

### 50. Sports Score Display
**Difficulty:** ⭐⭐⭐⭐
**Features:** Live game tracking

**Implementation:**
- Fetch live scores
- Team colors when winning
- Flash when scoring
- Celebration effect on win

**APIs:**
- ESPN API
- TheScore
- Team-specific APIs

---

## Contributing Your Projects

Built something cool? Share it!

1. **Document your project:**
   - Materials list
   - Wiring diagram
   - Configuration details
   - Photos/videos

2. **Create preset:**
   - Export your WLED configuration
   - Add to Presets.md with description

3. **Submit:**
   - Fork this repository
   - Add your project here
   - Submit pull request

---

## Resources for Project Planning

### CAD/Design Tools
- Fusion 360 (3D modeling)
- FreeCAD (open-source 3D)
- Inkscape (2D design)
- LED Strip Studio (virtual LED visualization)

### LED Calculators
- Power consumption: https://www.leds.de/
- Voltage drop: https://www.rapidtables.com/calc/wire/voltage-drop-calculator.html
- Wire gauge: https://www.calculator.net/voltage-drop-calculator.html

### Community Resources
- WLED Discourse: https://wled.discourse.group/
- Reddit: r/WLED
- Discord: Join via WLED GitHub
- YouTube: Search "WLED projects"

---

## Safety Reminders

- Calculate power requirements before buying supplies
- Use proper fuses and circuit protection
- Follow electrical codes for permanent installations
- Use weatherproof components outdoors
- Don't exceed LED strip current ratings
- Provide adequate cooling for high-density installations
- Use proper wire gauges to prevent voltage drop and fire hazards

---

**Get Creative and Share Your Builds! 🚀💡**

What will you build next?
