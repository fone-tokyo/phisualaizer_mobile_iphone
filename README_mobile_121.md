# PHISUALAIZER MOBILE v1.2.1

**PHISH-inspired lighting visualizer — Mobile Edition**
Inspired by CK5 (Chris Kuroda) / Created by FONE.TOKYO PROJECT

---

## What is PHISUALAIZER MOBILE?

A mobile-optimized version of PHISUALAIZER, designed for **iPhone Safari**.
Control the light show from your iPhone while the visuals play on a TV or projector independently — just like a real lighting operator.

Built with Three.js. No installation required.

---

## Disclaimer

This is an **unofficial fan-made project**.
Not affiliated with, endorsed by, or connected to Phish, CK5 (Chris Kuroda), or any related organizations.

This software is provided "as is", without warranty of any kind.
The authors are not responsible for any damages, injuries, or issues arising from the use of this software.
Use at your own risk.

---

## Warning

The **BLINK** feature produces flashing lights.
Flashing lights may cause photosensitive seizures in some people.

- Use the BLINK feature with caution.
- Not recommended for public events without prior warning to attendees.
- BLINK speed is limited to a safe range automatically.
- If you experience discomfort, dizziness, or seizures, stop use immediately.

---

## System Requirements

| Device | Requirement |
|--------|-------------|
| Controller | iPhone (Safari) |
| TV output device | Fire TV Stick / Smart TV with browser |
| Network | **Same WiFi network — required** |

> **WiFi is mandatory.** This system does not work without a shared WiFi network between your iPhone and the TV-side device.

---

## How It Works

PHISUALAIZER MOBILE uses a **WiFi cast architecture** — the same concept as YouTube casting.

```
iPhone (Controller)
  → Opens phisualaizer_mobile_121_iphone.html
  → Sends lighting state via BroadcastChannel over WiFi

TV-side device (Fire TV / Smart TV)
  → Opens phisualaizer_view_wifi.html from GitHub Pages
  → Renders visuals independently
  → Your iPhone screen is NOT shown on the TV
```

The TV renders visuals on its own. Your iPhone screen stays as the control panel only — the audience never sees the controls.

---

## Files

| File | Device | Description |
|------|--------|-------------|
| `phisualaizer_mobile_121_iphone.html` | iPhone | Controller — open in Safari |
| `phisualaizer_view_wifi.html` | Fire TV / Smart TV | Visual output — open in browser |

---

## Setup: TV Output (Step by Step)

### Step 1 — Connect to the same WiFi

Make sure your **iPhone** and your **TV-side device** (Fire TV Stick, Smart TV) are connected to the **same WiFi network**.

> ⚠️ If they are on different networks, the visual will not sync. This is the most common cause of issues.

---

### Step 2 — Open the view file on your TV

On your TV-side device, open a browser and go to:

```
https://fone-tokyo.github.io/phisualaizer_mobile_iphone/phisualaizer_view_wifi.html
```

**Fire TV Stick:**
1. Open Silk Browser (pre-installed)
2. Type the URL above in the address bar
3. The visual will load and show: `WAITING FOR CONTROL`

**Smart TV (built-in browser):**
1. Open the browser app
2. Type the URL above

> The view file must be loaded from **GitHub Pages (https://)** — not from a local file. BroadcastChannel requires the same origin to communicate.

---

### Step 3 — Open the controller on your iPhone

On your iPhone, open Safari and go to:

```
https://fone-tokyo.github.io/phisualaizer_mobile_iphone/phisualaizer_mobile_121_iphone.html
```

Or add it to your Home Screen for full-screen app experience:
1. Tap the Share button in Safari
2. Tap **Add to Home Screen**
3. Tap Add
4. Launch from Home Screen — runs fullscreen

---

### Step 4 — Confirm connection

Once both files are open on the same WiFi, the TV screen should change from:

```
WAITING FOR CONTROL  →  CONNECTED
```

The visuals will begin responding to your iPhone controls immediately.

---

## What Works / What Doesn't

### ✅ Works

- iPhone Safari → TV via WiFi cast (Fire TV Stick, Smart TV browser)
- All light controls (L1–L6), COMBO, PARTICLE, CAMERA
- Audio file playback and particle reaction on iPhone
- Add to Home Screen (PWA) for fullscreen controller

### ❌ Does NOT work

| Limitation | Reason |
|------------|--------|
| **No WiFi = no TV sync** | BroadcastChannel requires shared network |
| **HDMI mirroring from iPhone** | Shows controller UI on TV — not supported as TV output method |
| **Local file (file://) on TV** | Must open from GitHub Pages (https://) — local files block BroadcastChannel |
| **Android** | Not tested. May work on Chrome for Android but not guaranteed |
| **iPhone Chrome / other iOS browsers** | All iOS browsers use WebKit. Safari recommended |
| **Offline use for TV output** | TV-side device needs internet access to load from GitHub Pages |

> **Karaoke venues, live houses, and locations without accessible WiFi:** TV output is not possible. The iPhone controller works standalone for preview purposes only.

---

## Installation (iPhone)

No installation required.

**Recommended: Add to Home Screen**

1. Open Safari on iPhone
2. Go to the GitHub Pages URL above
3. Tap Share → Add to Home Screen
4. Launch from Home Screen for fullscreen experience

---

## Features

- **6 Light Groups** — CEILING / WALL-HI / FLOOR / LEFT / RIGHT / MV (26 beams total)
- **Individual Control** — Length, Speed, Spread, Hue, Brightness, Blink per light
- **SYNC Lock** — Lock any parameter column so all lights move together in real time
- **Particle Effects** — FLURRY / SPARKS / RAIN / ORBIT / BURST / DRIFT (collapsible panel)
- **Audio Reactive** — Load audio file and particles react to the music
- **Camera Control** — ORBIT / DISTANCE / HEIGHT / FOV
- **AUTO** — Parameters change slowly and automatically
- **SLOW / STOP** — STOP freezes lights only; particles keep running independently
- **GROUP** — Phase sync control per light
- **COMBO** — 2001 performance combo triggers (toggle mode)

---

## COMBO — 2001 Performance Mode

| Button | Effect |
|--------|--------|
| C1 | L2 lights up from the back |
| C2 | L2 + L1 join in |
| C3 | L2 + L1 + L3 — full build |
| C4 | ALL lights — flash → freeze → sparkle fade |

Tap to activate, tap again to release.
C4 triggers the full sequence automatically:
- Full blast → 3-second freeze → 5-second sparkle fadeout → back to normal

---

## How it was made

Built through a conversation with **Claude (AI by Anthropic)**.

No traditional coding was done by the author.
Pure collaboration between human vision and AI execution.

- The idea, creative direction, and all design decisions — **human**
- The code — **AI-generated**

---

## License

MIT License — Free to use, modify, and distribute.

**Commercial use:** Credit required.
Please include: `Based on PHISUALAIZER by FONE.TOKYO`

---

## Credits

- Inspired by **Chris Kuroda (CK5)** — PHISH lighting director
- Built with [Three.js r128](https://threejs.org/)
- Created by **FONE.TOKYO PROJECT**
- Built in collaboration with **Claude by Anthropic**
- `github.com/fone-tokyo/phisualaizer_mobile_iphone`

---

## Version History

| Version | Date | Notes |
|---------|------|-------|
| v1.2.0 | 2026.06.06 | Initial mobile release — WiFi cast architecture / iPhone Safari / PWA support |
| v1.2.1 | 2026.06.13 | L1 ceiling sweep improved / L4-L5 swing range expanded / L3 floor offset added |

---

## Related

**PC Version:** `github.com/fone-tokyo/phisualaizer`
Dual screen TV output via HDMI — no WiFi required.

---

*For PHANS, by a PHAN.*
