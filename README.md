# Mantle Verify

> Companion **diagnostics app** for the Mantle ecosystem. See exactly what device, network, location, and account identifiers a regular Android app can read — and verify your LSPosed/Xposed spoofing hooks in real time.

<p align="center">
  <img src="https://github.com/user-attachments/assets/f5d83a3d-384d-4f12-84f8-b95a22eecd70" alt="Home" width="49%" />
  <img src="https://github.com/user-attachments/assets/bccfbf98-9d98-49f9-8324-014f4eae9881" alt="About" width="49%" />
</p>

---

## Overview

**Mantle Verify** shows the identifiers, signals, and environment data that ordinary Android apps can access on your device.  
When Mantle’s LSPosed/Xposed hooks are active for `com.mantle.verify`, the app reflects the **virtualized (spoofed)** values — making it easy to confirm your per-app identity, GPS spoofing, timezone spoofing, and anti-fingerprinting setup.

**Now enhanced in v2.0.0 with:**
- **Location Panel:** live coordinates + full address (reverse-geocoded), spoof detection  
- **Timezone Panel:** system timezone, UTC offset, spoof verification  
- **Copy All / Export Report:** one-tap full device diagnostic export  
- **Remote-Config Ads:** Firebase-controlled placements (enable/disable instantly)  
- **Improved About Screen:** Mantle links, version info, theme selector  

---

## Sections Displayed

- **Location (NEW)** – coordinates, full address, spoofed GPS values  
- **Timezone (NEW)** – region + UTC offset, spoof spoof-detection  
- **Device / OS**
- **Network & SIM**
- **Wi-Fi & Bluetooth**
- **Google / Account IDs**
- **DRM & Media**
- **Phone Number**
- **Exportable Diagnostic Report (NEW)**

---

## Download

- Download the latest **signed APK** from **[Releases](../../releases)**.

> This project is **binary-only**. Source code is not publicly available.

---

## Requirements

- Android **7.0+ (API 24+)**  
- Optional: **LSPosed/EdXposed** to view spoofed values  
- Internet required for:
  - Full address lookup (reverse geocoding)
  - Remote Config toggles
  - External links

---

## Features (v2.0.0)

### 🔍 Core Diagnostics
- Real vs spoofed ID visibility
- Modern Material 3 UI
- Per-section copy buttons

### 🌍 Location Intelligence (NEW)
- Real-time GPS coordinates
- Full address via reverse geocoding  
- Detects if GPS is spoofed (when Mantle hooks active)
- Copy individual fields or **Copy All**

### 🕒 Timezone Panel (NEW)
- System timezone name
- UTC offset
- Spoofed timezone reflection (if Mantle is modifying it)

### 📄 Export Report (NEW)
- One-tap “Share Diagnostic Report”
- Includes all captured identifiers
- Ideal for debugging Mantle Console spoof setups

### 📡 Network & Radio
- SIM operator, MCC/MNC
- IMSI*, ICCID*
- Network type & signal basics

### 📶 Wi-Fi & Bluetooth
- SSID / BSSID
- Wi-Fi MAC*  
- Bluetooth MAC*

### 🔐 Google & IDs
- Android ID
- GSF ID
- Advertising ID
- Primary Gmail (masked)

### 🎥 DRM & Media
- Widevine Device Unique ID  
- Security level info

### 🎨 UI & About Enhancements
- New revamped About screen
- Theme selector (System / Light / Dark)
- Mantle website + Telegram links

### 📢 Remote-Config Ads (Firebase)
- Per-placement control:
  - Below Network
  - Below Google IDs
  - Below Links (About Screen)

---

## Permissions

Mantle Verify requests only the minimal required permissions:

- `READ_PHONE_STATE`, `READ_PHONE_NUMBERS`
- `ACCESS_FINE_LOCATION`, `ACCESS_COARSE_LOCATION`
- `ACCESS_WIFI_STATE`, `BLUETOOTH_CONNECT`
- `INTERNET`, `ACCESS_NETWORK_STATE`

Due to Android restrictions, some IDs may show as unavailable unless permitted.

---

## Installation

1. Download the latest APK from **[Releases](../../releases)**  
2. Enable "Install unknown apps"  
3. Install  
4. (Optional) Enable Mantle hooks via LSPosed and include `com.mantle.verify` in scope

---

## FAQ

**Q: Do I need LSPosed?**  
No. Without LSPosed, you see actual system values. With LSPosed (+ Mantle hooks), you see spoofed values.

**Q: Why does some info show “Restricted”?**  
Newer Android versions block some identifiers unless you grant proper permissions.

---

## Roadmap

- LSPosed / Xposed Module Repository listing  
- More sensor-based fingerprinting visibility  
- Device integrity signals  
- Per-permission visibility map  
- Cloud-based signature comparison

---

## Privacy

- No background data collection  
- Reads only what normal apps can access  
- Reverse-geocoding addresses is performed locally or via system geocoder

---

## Contact & Links

- Website: **https://getmantle.in**  
- Telegram: **@getmantle**  
- Feedback / Bug Reports: GitHub Issues  

---

## License

Binary distribution only — all rights reserved.  
Redistribution, modification, or repackaging of the APK or assets is not allowed without permission.
