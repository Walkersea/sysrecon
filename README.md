# SYSRECON

SYSRECON is a lightweight, single-file browser diagnostic tool designed with a high-fidelity "cyberpunk" terminal aesthetic. It provides a comprehensive overview of your system's hardware, network identity, and browser fingerprinting profile—all from within a standard web page.

## Key Features

* **System Identity & Browser Profiling:** Instantly pulls OS platform data, CPU core counts, device RAM, and detailed browser engine information.
* **Hardware Diagnostics:** Monitors real-time battery levels, charging status, and JS memory heap usage.
* **Network Intel:** Fetches public IP, ISP details, and geographic location (pending user permission), alongside built-in speed and ping testing tools.
* **Digital Fingerprinting:** Demonstrates how websites identify users by generating unique hashes for Canvas, WebGL, and Audio contexts.
* **Display Matrix:** Breaks down screen resolution, color depth, pixel ratios, and HDR support.
* **Advanced Recon:** Checks for modern web API support (Web Crypto, Credential Manager, etc.) and analyzes CSS rendering capabilities.

## Technical Overview

The project is built using:
* **HTML5 & CSS3:** Leverages advanced CSS features like custom variables, backdrop filters, and glitch animations to create an immersive UI.
* **Vanilla JavaScript:** Uses native Web APIs (Navigator, WebGL, Battery Status, Performance API) for data collection with no external library dependencies.
* **Typography:** Utilizes Google Fonts ('Orbitron', 'Share Tech Mono', and 'VT323') to reinforce the retro-futurist terminal look.

## How to Run

1.  Download the `sysrecon.html` file.
2.  Open the file in any modern web browser (Chrome, Firefox, or Edge).
3.  The "Deep Scan" will initialize automatically upon loading.

*Note: For the most accurate network and hardware readings, some features may request permission (like Geolocation or Media Devices).*

## Security & Privacy

SYSRECON is a client-side tool. While it fetches IP/ISP data from external APIs, the system data it collects remains in your browser. This project is intended for educational use, diagnostics, and demonstrating the transparency of modern web privacy.
