# Mantle Verify

> Companion **diagnostics app** for the Mantle ecosystem. See exactly what device, network, location, and account identifiers a regular Android app can read — and verify your LSPosed/Xposed spoofing hooks in real time.

<p align="center">
  <img src="https://raw.githubusercontent.com/get-mantle/Mantle-Verify/refs/heads/main/Home.png" alt="Home" width="24%" />
  <img src="https://raw.githubusercontent.com/get-mantle/Mantle-Verify/refs/heads/main/red.png" alt="Detector Red" width="24%" />
  <img src="https://raw.githubusercontent.com/get-mantle/Mantle-Verify/refs/heads/main/green.png" alt="Detector Green" width="24%" />
  <img src="https://raw.githubusercontent.com/get-mantle/Mantle-Verify/refs/heads/main/about.png" alt="About" width="24%" />
</p>

---

## Overview

**Mantle Verify** shows the identifiers, signals, and environment data that ordinary Android apps can access on your device.  
When Mantle’s LSPosed/Xposed hooks are active for `com.mantle.verify`, the app reflects the **virtualized (spoofed)** values — making it easy to confirm your per-app identity, GPS spoofing, timezone spoofing, and anti-fingerprinting setup.

---

## What’s New in v2.1.0

### 🛡️ Environment / Root Detector (New Screen)
- Added a dedicated **“Environment / Root Detector”** screen to quickly assess whether the device looks rooted or heavily modified.
- Clear **Green = clean / Red = suspicious** status for each check.
- Summary line showing overall status, e.g.  
  `Status: Looks clean for all checks.` or  
  `Status: Root / modifications detected (N red checks).`
- One-tap **floating action button** to re-run all checks.

### 🔍 Root & Xposed / LSPosed Detection
- Detects **root / patch frameworks** like:
  - Magisk (stable / forks)  
  - KernelSU  
  - APatch  
  - Shizuku (privileged API)
- Detects **Xposed / LSPosed managers & related apps**:
  - LSPosed Manager  
  - EdXposed Manager  
  - Classic Xposed Installer  
  - TaiChi  
  - Hide My Applist (HMA)
- Scans installed apps for **Xposed / LSPosed modules** via classic manifest meta-data keys:
  - `xposedmodule`  
  - `xposedmoduleminversion`  
  - `xposedminversion`
- Flags additional environment signals:
  - `su` / BusyBox binaries in common paths  
  - RW mounts on `/system`, `/vendor`, `/odm`  
  - Dangerous system properties (`ro.debuggable=1`, `ro.secure=0`, unlocked vbmeta)  
  - Root-hider / cloaker apps (HMA, App Ops, Sui)  
  - SELinux mode via `getenforce` (permissive vs enforcing)  
  - Magisk traces and modules directory  
  - Xposed bridge class presence  
  - Signature spoof (`FAKE_PACKAGE_SIGNATURE`)  
  - Custom recovery traces (TWRP, recovery logs/scripts)

> Note: All checks are **heuristic**. A clever ROM or root-hider can still bypass them.
---

## Sections Displayed

- **Location (NEW)** – coordinates, full address, spoofed GPS values  
- **Timezone (NEW)** – region + UTC offset, spoof spoof-detection  
- **Environment / Root Detector (NEW in v2.1.0)** – root frameworks, su/busybox, Magisk traces, SELinux mode, Xposed/LSPosed managers & modules, signature spoof, recovery traces  
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

## Features

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
