# Speed Radar

Camera-based vehicle speed detection that runs in your phone browser. Point your phone at the road, calibrate once, and it continuously monitors traffic speed.

## How It Works

Uses your phone's camera and computer vision (frame differencing) to detect moving vehicles, track them across frames, and calculate their speed based on calibration data you provide.

**Accuracy:** ~10-20% with good calibration. Best for identifying clear speed limit violations (25 vs 45 mph), not precise measurement.

## Quick Start

1. Open the app on your phone (use GitHub Pages link or serve locally)
2. Complete the 4-step calibration:
   - **Distance to road** — measure from your phone to the center of the nearest lane
   - **Camera height** — how high the phone is from the ground
   - **Road width** — width of the road surface
   - **Camera angle** — perpendicular gives best results
3. Prop your phone up facing the road
4. The app continuously monitors for vehicles and logs speeds

## Features

- **Continuous passive monitoring** — always watching, no button press needed
- **Night mode** — detects headlights automatically (or toggle manually)
- **Speed alerts** — screen flashes red when vehicles exceed your set limit
- **Speed logging** — every detection saved with timestamp and direction
- **CSV export** — download your speed data
- **Calibration wizard** — guided setup with recalibration anytime
- **Settings panel** — units, sensitivity, alerts, camera selection, wake lock

## Settings

| Setting | Options | Default |
|---------|---------|---------|
| Speed Units | MPH / KM/H | MPH |
| Speed Limit | 5-100 | 25 |
| Visual Alerts | On/Off | On |
| Sound Alerts | On/Off | Off |
| Sensitivity | Low/Medium/High | Medium |
| Night Mode | Auto/On/Off | Auto |
| Camera | Front/Back | Back |
| Show Tracking | On/Off | On |
| Wake Lock | On/Off | On |

## Tips for Best Results

- **Mount your phone steady** — a window sill, tripod, or phone holder works great
- **Point perpendicular to traffic** — angled views reduce accuracy
- **Measure carefully** — the distance-to-road measurement matters most
- **Medium sensitivity** works for most conditions; use High for distant roads
- **Calibrate in daylight first** — night mode works but daytime is more reliable

## Running Locally

Just open `index.html` in a browser. For phone access, you can:

```bash
# Simple Python server
python3 -m http.server 8000

# Then open on your phone (same WiFi network):
# http://YOUR_COMPUTER_IP:8000
```

Or deploy to GitHub Pages for easy phone access over HTTPS (required for camera API).

## Privacy

All processing happens locally in your browser. No data is sent anywhere. Speed logs are stored in your browser's localStorage.

## Limitations

- Accuracy depends on calibration quality
- Works best with single vehicles (multiple overlapping cars may confuse tracking)
- Very fast vehicles may be underestimated due to frame rate
- Requires HTTPS for camera access (use GitHub Pages or localhost)
