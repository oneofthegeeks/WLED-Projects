# WLED Multi-Segment Presets

This file contains advanced WLED presets that use multiple segments to create complex lighting patterns. Each segment can have different colors and effects.

---

## Rainbow Sections
*7 segments with different solid colors creating a rainbow pattern*

**Segment Layout:**
- Segment 0 (LEDs 0-15): Red & White
- Segment 1 (LEDs 15-30): Blue
- Segment 2 (LEDs 30-45): Green
- Segment 3 (LEDs 45-60): Magenta
- Segment 4 (LEDs 60-75): White
- Segment 5 (LEDs 75-90): Blue
- Segment 6 (LEDs 90-100): Red

```json
{
  "on": true,
  "bri": 255,
  "transition": 7,
  "mainseg": 0,
  "seg": [
    {
      "id": 0,
      "start": 0,
      "stop": 15,
      "grp": 1,
      "spc": 0,
      "of": 0,
      "on": true,
      "frz": false,
      "bri": 255,
      "cct": 127,
      "set": 0,
      "n": "",
      "col": [[255, 0, 0], [255, 255, 255], [255, 0, 0]],
      "fx": 0,
      "sx": 128,
      "ix": 128,
      "pal": 50,
      "c1": 128,
      "c2": 128,
      "c3": 16,
      "sel": true,
      "rev": false,
      "mi": false,
      "o1": false,
      "o2": false,
      "o3": false,
      "si": 0,
      "m12": 0
    },
    {
      "id": 1,
      "start": 15,
      "stop": 30,
      "grp": 1,
      "spc": 0,
      "of": 0,
      "on": true,
      "frz": false,
      "bri": 255,
      "cct": 127,
      "set": 0,
      "n": "",
      "col": [[0, 0, 255], [0, 0, 0], [0, 0, 0]],
      "fx": 0,
      "sx": 128,
      "ix": 128,
      "pal": 50,
      "c1": 128,
      "c2": 128,
      "c3": 16,
      "sel": true,
      "rev": false,
      "mi": false,
      "o1": false,
      "o2": false,
      "o3": false,
      "si": 0,
      "m12": 0
    },
    {
      "id": 2,
      "start": 30,
      "stop": 45,
      "grp": 1,
      "spc": 0,
      "of": 0,
      "on": true,
      "frz": false,
      "bri": 255,
      "cct": 127,
      "set": 0,
      "n": "",
      "col": [[8, 255, 0], [0, 0, 0], [0, 0, 0]],
      "fx": 0,
      "sx": 128,
      "ix": 128,
      "pal": 50,
      "c1": 128,
      "c2": 128,
      "c3": 16,
      "sel": true,
      "rev": false,
      "mi": false,
      "o1": false,
      "o2": false,
      "o3": false,
      "si": 0,
      "m12": 0
    },
    {
      "id": 3,
      "start": 45,
      "stop": 60,
      "grp": 1,
      "spc": 0,
      "of": 0,
      "on": true,
      "frz": false,
      "bri": 255,
      "cct": 127,
      "set": 0,
      "n": "",
      "col": [[255, 0, 255], [0, 0, 0], [0, 0, 0]],
      "fx": 0,
      "sx": 128,
      "ix": 128,
      "pal": 50,
      "c1": 128,
      "c2": 128,
      "c3": 16,
      "sel": true,
      "rev": false,
      "mi": false,
      "o1": false,
      "o2": false,
      "o3": false,
      "si": 0,
      "m12": 0
    },
    {
      "id": 4,
      "start": 60,
      "stop": 75,
      "grp": 1,
      "spc": 0,
      "of": 0,
      "on": true,
      "frz": false,
      "bri": 255,
      "cct": 127,
      "set": 0,
      "n": "",
      "col": [[255, 255, 255], [0, 0, 0], [0, 0, 0]],
      "fx": 0,
      "sx": 128,
      "ix": 128,
      "pal": 50,
      "c1": 128,
      "c2": 128,
      "c3": 16,
      "sel": true,
      "rev": false,
      "mi": false,
      "o1": false,
      "o2": false,
      "o3": false,
      "si": 0,
      "m12": 0
    },
    {
      "id": 5,
      "start": 75,
      "stop": 90,
      "grp": 1,
      "spc": 0,
      "of": 0,
      "on": true,
      "frz": false,
      "bri": 255,
      "cct": 127,
      "set": 0,
      "n": "",
      "col": [[0, 0, 255], [0, 0, 0], [0, 0, 0]],
      "fx": 0,
      "sx": 128,
      "ix": 128,
      "pal": 50,
      "c1": 128,
      "c2": 128,
      "c3": 16,
      "sel": true,
      "rev": false,
      "mi": false,
      "o1": false,
      "o2": false,
      "o3": false,
      "si": 0,
      "m12": 0
    },
    {
      "id": 6,
      "start": 90,
      "stop": 100,
      "grp": 1,
      "spc": 0,
      "of": 0,
      "on": true,
      "frz": false,
      "bri": 255,
      "cct": 127,
      "set": 0,
      "n": "",
      "col": [[255, 0, 0], [0, 0, 0], [0, 0, 0]],
      "fx": 0,
      "sx": 128,
      "ix": 128,
      "pal": 50,
      "c1": 128,
      "c2": 128,
      "c3": 16,
      "sel": true,
      "rev": false,
      "mi": false,
      "o1": false,
      "o2": false,
      "o3": false,
      "si": 0,
      "m12": 0
    }
  ]
}
```

---

## Understanding Multi-Segment Configurations

### Key Parameters

| Parameter | Description |
|-----------|-------------|
| `id` | Segment ID number (0-31) |
| `start` | First LED in segment |
| `stop` | Last LED in segment (exclusive) |
| `on` | Segment enabled |
| `bri` | Segment brightness (0-255) |
| `col` | Color array [Primary, Secondary, Tertiary] |
| `fx` | Effect ID (0 = solid color) |
| `sx` | Effect speed |
| `ix` | Effect intensity |
| `pal` | Palette ID |
| `grp` | Grouping (virtual LED length) |
| `spc` | Spacing (gap between virtual LEDs) |

### How to Apply

**Using cURL:**
```bash
curl -X POST http://[WLED-IP]/json/state \
  -H "Content-Type: application/json" \
  -d @multi-segment-config.json
```

**Using Browser Console:**
```javascript
fetch('/json/state', {
  method: 'POST',
  headers: {'Content-Type': 'application/json'},
  body: JSON.stringify(YOUR_CONFIG_HERE)
});
```

### Customizing Segments

To modify this preset for your setup:

1. **Adjust LED counts**: Change `start` and `stop` values to match your strip length
2. **Change colors**: Modify the `col` arrays with your desired RGB values
3. **Add effects**: Change `fx` from 0 to any effect ID
4. **Adjust brightness**: Modify `bri` per segment or globally

### Tips for Multi-Segment Setups

- Use segments to create zones in your room
- Different segments can run different effects simultaneously
- Segments can overlap for layered effects
- Use grouping (`grp`) and spacing (`spc`) for creative patterns
- Save complex configurations as presets in WLED for easy recall

---

## Example Use Cases

### Room Zones
- Segment 1: Desk area (cool white for work)
- Segment 2: Bed area (warm white for relaxation)
- Segment 3: Entertainment area (colorful for ambiance)

### Architectural Accent
- Segment 1: Floor level (dim, warm)
- Segment 2: Mid-wall (medium brightness)
- Segment 3: Ceiling (bright, accent color)

### Party Mode
- Each segment cycles through different effects
- Create "waves" of color across the room
- Synchronized segment changes for dramatic effect

---

*Add your own multi-segment configurations below!*
