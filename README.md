# Mantle Verify

> Companion **diagnostics app** for the Mantle ecosystem. See exactly what device, network, and account identifiers a regular Android app can read — and verify your LSPosed/Xposed spoofing hooks in real time.

<p align="center">
  <img src="https://github.com/user-attachments/assets/f5d83a3d-384d-4f12-84f8-b95a22eecd70" alt="Home" width="49%" />
  <img src="https://github.com/user-attachments/assets/bccfbf98-9d98-49f9-8324-014f4eae9881" alt="About" width="49%" />
</p>

---

## Overview

**Mantle Verify** shows the identifiers and signals that ordinary Android apps can access on your device.  
When Mantle’s LSPosed/Xposed hooks are active for `com.mantle.verify`, this app reflects the **virtualized (spoofed)** values — making it easy to confirm your per-app identity configuration and anti-fingerprinting setup.

- **Device/OS:** model, Android version, build fingerprint  
- **Network & SIM:** operator, MCC/MNC, IMSI*, ICCID*  
- **Wi-Fi & Bluetooth:** SSID, Wi-Fi MAC*, Bluetooth MAC*  
- **Google / IDs:** Android ID, Advertising ID, GSF `android_id`, primary Gmail (masked)  
- **DRM / Media:** Widevine **DEVICE_UNIQUE_ID** (hex)  

\* Some identifiers are restricted or randomized on newer Android versions without special privileges.

---

## Download

- Get the latest **signed APK** from **[Releases](../../releases)**.

> This repository is **binary-only**. Source code is not published.

---

## Requirements

- Android **7.0+ (API 24+)**  
- (Optional) **LSPosed/EdXposed** if you want to view spoofed values from Mantle hooks  
- Internet access (for update checks and external links)

---

## Features

- **At-a-glance verification** of spoofed vs system IDs  
- **Sections:** Device Info; IMEI/Device IDs; Network & Radio; Wi-Fi & Bluetooth; Google/IDs; DRM & Media; Phone Number  
- Minimal, Material 3 UI with safe insets

---

## Permissions

Mantle Verify requests a minimal set of runtime permissions to display what ordinary apps can see:

- `READ_PHONE_STATE`, `READ_PHONE_NUMBERS` – telephony identifiers (varies by Android version)  
- `ACCESS_WIFI_STATE`, `ACCESS_FINE_LOCATION`, `ACCESS_COARSE_LOCATION` – Wi-Fi SSID/MAC visibility  
- `BLUETOOTH_CONNECT` – Bluetooth MAC visibility on newer Android  
- `INTERNET`, `ACCESS_NETWORK_STATE` – network access for in-app features

Some values may display as unavailable due to OS restrictions or missing permissions.

---

## Installation

1. Download `app-release.apk` from **[Releases](../../releases)**.  
2. Enable “Install unknown apps” for your browser or file manager.  
3. Install the APK.  
4. (Optional) If you’re using Mantle hooks, ensure **LSPosed** is active and your target apps + `com.mantle.verify` are in scope.

---

## FAQ

**Q: Do I need LSPosed to use this?**  
A: No. Without LSPosed, the app shows the **actual** system values. With Mantle hooks active, it shows the **virtualized** values — useful for verification.

**Q: Why do some fields show “restricted/unavailable”?**  
A: Newer Android versions restrict access to certain IDs. That’s expected behavior unless you have special permissions or hooks.

---

## Versioning

This project follows **[Semantic Versioning](https://semver.org/)**:
- Format: **MAJOR.MINOR.PATCH** (e.g., `1.0.0`)
- Pre-releases: `1.1.0-beta.1`, `1.1.0-rc.1`, etc.

See **[Releases](../../releases)** for the changelog.

---

## Roadmap

- LSPosed Module Repository listing  
- More diagnostics (per-permission visibility hints, export/share report)  
- Optional dark-mode screenshots in release assets

---

## Privacy

- The app reads only what typical Android apps can access, gated by runtime permissions you approve.
- No background collection beyond what is necessary for core functionality.

---

## Contact & Links

- Website: **https://getmantle.in**  
- Telegram: **@getmantle**  
- Issues / feedback: open a **GitHub Issue** on this repo

---

## License

Binary distribution only. All rights reserved.  
You may **download and use the APK**, but redistribution or modification of the binary, assets, and brand elements is not permitted without prior written consent.
