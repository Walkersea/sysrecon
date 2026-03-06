# 💾 SYSRECON — Deep Scan v2.1
https://walkersea.github.io/sysrecon/sysrecon.html<br>
> A hacker-aesthetic browser-based system profiler that extracts every possible data point from the user's machine — no backend, no installs, pure client-side.

![HTML](https://img.shields.io/badge/HTML-single%20file-00ff41?style=flat-square&labelColor=020a04) ![JS](https://img.shields.io/badge/JavaScript-vanilla-00ff41?style=flat-square&labelColor=020a04) ![CSS](https://img.shields.io/badge/CSS-pure-00ff41?style=flat-square&labelColor=020a04) ![Dependencies](https://img.shields.io/badge/dependencies-zero-00ff41?style=flat-square&labelColor=020a04)

---

## 🖥 What It Does

SYSRECON runs a full deep scan of the browser environment and renders every extractable data point in a terminal-style dashboard. It also runs active diagnostics — ping sweeps, speed tests, and a PC performance rating — all without any server-side code.

---

## 📡 Data Points Extracted

### System Identity
- OS platform, CPU core count, device RAM
- Touch support, PDF viewer, cookies, Java, Do Not Track, online status

### Browser Profile
- App name & version, language & language list, vendor, product
- WebDriver detection, Service Worker support, Notification permission

### Display Matrix
- Screen resolution, available resolution, window & inner size
- Color depth, pixel depth, device pixel ratio, orientation
- Color gamut (sRGB / Display P3 / Rec2020), HDR support

### GPU / WebGL
- Renderer & vendor (standard + unmasked via `WEBGL_debug_renderer_info`)
- WebGL & GLSL version, max texture size, max viewport dims
- Max render buffer size, antialiasing support

### Network Intel
- Live public IP address (via ipapi.co)
- ISP, country, region, city, timezone
- Connection type, effective type, downlink speed, RTT, Save Data flag

### Time & Location
- Local time, UTC time, timezone, UTC offset, DST status
- GPS latitude, longitude, accuracy, altitude, speed (with permission)

### Battery Status
- Charge level (%), charging state, charging time, discharging time
- Visual charge bar

### Memory & Performance
- JS heap limit, total heap, used heap
- Page load time, DOM interactive time, DNS lookup, TCP connect, TTFB
- Transfer size, total resources loaded

### Digital Fingerprint
- Canvas 2D hash, WebGL hash, Web Audio hash
- Detected font count, plugin count
- localStorage / sessionStorage / IndexedDB availability
- WebRTC support, incognito mode estimation, AdBlock detection

### Media Devices
- Camera count, microphone count, speaker count
- WebAudio, MIDI, Gamepad, Bluetooth, USB, VR/AR, Screen Capture

### Security & APIs
- HTTPS detection, Web Crypto API, Credentials Manager
- Payment API, Share API, Clipboard API, Permissions API
- Storage API, Idle Detection, Screen Capture API

### CSS & Rendering
- Dark mode preference, reduced motion, contrast preference, forced colors
- CSS Grid, CSS Variables, Flexbox, Animations, Backdrop Filter
- Pointer type (mouse / touch / none)

### Browser Plugins
- Full enumerated list of installed browser plugins

### User Agent
- Full raw UA string with parsed badges (Chrome, Firefox, Safari, Edge, Mobile, OS, Bot detection)

---

## ⚡ Active Diagnostics

### 🎯 PC Performance Rating (1–10)
Scores the machine across five dimensions and produces an overall rating:

| Dimension | Source |
|-----------|--------|
| CPU | `navigator.hardwareConcurrency` |
| Memory | `navigator.deviceMemory` |
| GPU | WebGL unmasked renderer string |
| Display | Screen pixel count |
| Network | Connection API effective type + downlink |

Labels range from **ANCIENT** (1) to **GODLIKE** (10).

### 📶 Ping Sweep
Sends `HEAD` / `no-cors` requests to 5 real endpoints and reports individual + average round-trip time:
- Cloudflare DNS, Google DNS, OpenDNS, ipapi.co, JSONPlaceholder

### ⚡ Speed Test
Downloads real CDN-hosted files (three.js, lodash) with cache-busting, measures elapsed time, and calculates download speed in Mbps alongside a latency measurement.

---

## 🛡 Threat Level

Analyzes the session for privacy/anonymity signals and produces a threat rating (NONE → CRITICAL):

- WebDriver / bot flag detected
- Cookies disabled
- AdBlock detected
- Incognito mode estimated
- Do Not Track enabled

---

## 🚀 Usage

No build step. No dependencies. Just open the file.

```bash
# Option 1 — open directly
open sysrecon.html

# Option 2 — serve locally
npx serve .
# or
python3 -m http.server 8080
```

Then visit `http://localhost:8080/sysrecon.html`.

> **Tip:** Serve over HTTPS for full API access (Battery, Geolocation, Device Enumeration, Web Crypto).

---

## 🎨 Design

- **Font:** Orbitron (headers) + Share Tech Mono (data) + VT323 (large numerals)
- **Palette:** `#00ff41` green-on-black with amber and cyan accents
- **Effects:** CRT scanlines, vignette, animated noise overlay, glow text shadows, glitch animation on logo
- **Layout:** Responsive 3-column CSS Grid, collapses to 2-col and 1-col on smaller screens

---

## ⚠️ Notes

- **No data is transmitted** anywhere except the IP lookup call to `ipapi.co` and CDN files used for the speed test.
- Geolocation requires explicit browser permission grant.
- Some APIs (`Battery`, `deviceMemory`, `hardwareConcurrency`) may be restricted or spoofed by certain browsers for privacy reasons.
- The speed test result is an estimate based on CDN file downloads and may not reflect real ISP throughput.
- Works best in Chromium-based browsers for full API coverage.

---

## 📄 License

MIT — do whatever you want with it.
