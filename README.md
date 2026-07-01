# DTB Selector — (d)ArkOS4Clone & dArkOS RE – Android Apk

![Platform](https://img.shields.io/badge/Platform-RK3326-blue)
![OS](https://img.shields.io/badge/OS-Android%208.0+-green)
![Language](https://img.shields.io/badge/Language-Kotlin-purple)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

DTB Selector is an Android app designed for RK3326-based handhelds (R36S, R36Pro, R36Max, clones, etc.) that allows easy selection and deployment of the correct Device Tree Blob files via an OTG SD card reader. **No PC required.**

The app supports **two OS targets**, selectable from a dropdown at the top of the screen:

| OS | Source config | What it does |
|---|---|---|
| **(d)ArkOS4Clone** | `consoles.json` should be placed in the boot directory of the SD card. | Brand/console/battery selection, full overclocking (CPU/GPU/DDR + voltage patch), patches `boot.ini`/`boot.txt` |
| **dArkOS RE** | `r36_devices.ini` included in your SD root | Variant/device selection, copies `.dtb` from `dtb/<variant>/<device>/`, installs the matching `logo.bmp` (640x480 / 720x720) |

Switching the OS dropdown reloads the correct config file and shows only the relevant options — no overclocking/battery UI for dArkOS RE, since that distro doesn't expose those concepts.

---

- **Brand & console selection** via simple dropdowns ((d)ArkOS4Clone) or **variant & device selection** (dArkOS RE)
- **2 battery driver versions** ((d)ArkOS4Clone only):
  - <img src="https://img.shields.io/badge/-Original-blue?style=flat-square"> → Original battery driver
  - <img src="https://img.shields.io/badge/-arkos4clone__fix-orange?style=flat-square"> → arkos4clone_fix battery driver

- **Safe file deployment**:
  - Automatically removes old `.dtb` / `.dtbo` / `Image` files before copying
  - ArkOS4Clone: copies DTB files from `consoles/<name>/` to SD root, plus the correct kernel `Image` and extra logo files
  - dArkOS RE: copies DTB files from `dtb/<variant>/<device>/` to SD root, plus the matching `logo.bmp`

- **Console/device list updatable** without reinstalling the app — just update `consoles.json` (to (d)Arkos4clone only) on the SD card
- **Real-time log** displayed during file operations

## 📋 Requirements / Important notes

- Android 8.0+
- OTG SD card reader
- SD card with the following structure:

## 🚀 Installation

1. Download the APK
2. Enable *Unknown Sources* on your Android device (Settings → Apps → your file manager → Install unknown apps)
3. Install the `.apk`
4. Pick your target OS in the app, then copy the matching config file (`consoles.json` or `r36_devices.ini`) plus its folder structure to the root of your SD card

---

## 🔄 Updating consoles / devices

- **(d)ArkOS4Clone**: update `consoles.json` folder on the SD card. No app update needed.
- **dArkOS RE**: automatic update 

---

## Thanks

Thanks to the RK3326 community for DTB contributions, lcdyk for DTB panels.

---

## ☕ A coffee to support the project?

[![Ko-fi](https://img.shields.io/badge/☕_Buy_me_a_coffee-jason3x-red?style=for-the-badge)](https://ko-fi.com/jason3x)
