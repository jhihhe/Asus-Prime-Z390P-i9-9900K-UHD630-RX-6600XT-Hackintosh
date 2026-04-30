# ASUS PRIME Z390-P Hackintosh EFI

<p align="center">
  <img src="https://img.shields.io/badge/macOS-Sonoma%2014.6.1-purple?style=for-the-badge" alt="macOS Sonoma">
  <img src="https://img.shields.io/badge/macOS-Ventura%2013.x-blue?style=for-the-badge" alt="macOS Ventura">
  <img src="https://img.shields.io/badge/macOS-Tahoe%2026.5-blue?style=for-the-badge&label=macOS+Tahoe+26.5" alt="macOS Tahoe 26.5">
  <img src="https://img.shields.io/badge/OpenCore-1.0.8%20MOD-green?style=for-the-badge" alt="OpenCore 1.0.8 MOD">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Z390-blue?style=for-the-badge" alt="Platform Z390">
  <img src="https://img.shields.io/badge/CPU-Intel%20i9%209900K-orange?style=for-the-badge" alt="Intel i9 9900K">
  <img src="https://img.shields.io/badge/GPU-RX%206600%20XT-red?style=for-the-badge" alt="AMD RX 6600 XT">
  <img src="https://img.shields.io/badge/GPU-UHD%20630-green?style=for-the-badge" alt="Intel UHD 630">
</p>

<p align="center">
  <a href="README.md">🇨🇳 简体中文</a> | <a href="#english">🇺🇸 English</a>
</p>

---

## 📋 Table of Contents

- [Project Introduction](#project-introduction)
- [Hardware Configuration](#hardware-configuration)
- [EFI Structure](#efi-structure)
- [Installation Guide](#installation-guide)
- [Kext Update Log](#kext-update-log)
- [Broadcom WiFi Driver Guide](#broadcom-wifi-driver-guide)
- [FAQ](#faq)
- [License](#license)
- [Contributing](#contributing)

---

## 🏠 Project Introduction

This project provides a complete OpenCore EFI configuration for the **ASUS PRIME Z390-P** desktop, supporting installation and running of macOS Sonoma, Ventura, Monterey, Catalina, and the latest **macOS 26 Tahoe**.

### ✨ Features

- ✅ macOS 15.x (Sonoma) to macOS 26.x (Tahoe) support
- ✅ OpenCore 1.0.8 MOD core
- ✅ Full hardware acceleration support
- ✅ Native Broadcom WiFi driver support
- ✅ Custom AMD Radeon Pro W6600X GPU configuration
- ✅ Graphical OpenCore boot interface
- ✅ SIP (System Integrity Protection) management support

---

## 💻 Hardware Configuration

| Component | Model | Status |
|-----------|-------|--------|
| Motherboard | ASUS PRIME Z390-P | ✅ Verified |
| CPU | Intel Core i9-9900K | ✅ Verified |
| iGPU | Intel UHD Graphics 630 | ✅ Verified |
| dGPU | AMD Radeon RX 6600 XT | ✅ Verified |
| Ethernet | Realtek RTL8111H | ✅ Verified |
| WiFi | Broadcom Hackintosh WiFi Card | ✅ Verified |
| Audio | Realtek ALC887 | ✅ Verified |
| RAM | DDR4 | ✅ Verified |

### 🔧 SMBIOS Configuration

```
Model: iMac19,1
Serial: C02DR0FJJV3Q
MLB: C02048802J9LNV9CB
UUID: 28A6D2F3-5152-4229-9A87-0E97331FF84D
```

---

## 📁 EFI Structure

```
EFI/
├── APPLE/
│   └── FIRMWARE/
│       └── IM191.fd
├── BOOT/
│   ├── .contentVisibility
│   └── BOOTx64.efi
└── OC/
    ├── ACPI/
    │   ├── SSDT-AWAC-DISABLE.aml    # AWAC clock disable
    │   ├── SSDT-PLUG.aml            # CPU power management
    │   └── SSDT-PMC.aml             # PMC fix
    ├── Drivers/
    │   ├── CrScreenshotDxe.efi      # Screenshot function
    │   ├── HfsPlus.efi               # HFS+ filesystem support
    │   ├── OpenCanopy.efi            # Graphical interface
    │   ├── OpenRuntime.efi           # Runtime driver
    │   ├── ResetNvramEntry.efi       # NVRAM reset
    │   └── ToggleSipEntry.efi        # SIP toggle tool
    ├── Kexts/
    │   ├── AMFIPass.kext             # AMFI patch delivery
    │   ├── AirportBrcmFixup.kext     # Broadcom WiFi fix
    │   ├── AppleALC.kext             # Audio driver
    │   ├── AppleALCU.kext            # USB audio driver
    │   ├── BlueToolFixup.kext        # Bluetooth fix
    │   ├── BrcmFirmwareData.kext     # Broadcom firmware data
    │   ├── BrcmPatchRAM3.kext        # Broadcom patch driver
    │   ├── IO80211FamilyLegacy.kext  # Legacy WiFi driver
    │   ├── IOSkywalkFamily.kext      # macOS 26 support
    │   ├── Lilu.kext                 # Base library
    │   ├── RadeonSensor.kext          # GPU sensor
    │   ├── RealtekRTL8111.kext       # Realtek ethernet
    │   ├── RestrictEvents.kext        # Event restriction
    │   ├── SMCProcessor.kext         # SMC processor
    │   ├── SMCRadeonGPU.kext         # AMD SMC support
    │   ├── SMCSuperIO.kext           # SuperIO sensor
    │   ├── USBPorts.kext             # USB port customization
    │   ├── VirtualSMC.kext           # SMC virtualization
    │   └── WhateverGreen.kext        # GPU fix
    ├── Resources/
    │   ├── Audio/                    # Boot sounds
    │   ├── Font/                     # Interface fonts
    │   ├── Image/jhih/Hackintosh/   # Theme images
    │   └── Label/                    # Label resources
    ├── Tools/
    │   ├── BootKicker.efi
    │   ├── ChipTune.efi
    │   ├── CleanNvram.efi
    │   ├── ControlMsrE2.efi
    │   ├── CsrUtil.efi
    │   ├── GopStop.efi
    │   ├── KeyTester.efi
    │   ├── MmapDump.efi
    │   ├── OpenControl.efi
    │   ├── OpenShell.efi
    │   ├── ResetSystem.efi
    │   ├── RtcRw.efi
    │   └── TpmInfo.efi
    ├── OpenCore.efi
    └── config.plist
```

---

## 🚀 Installation Guide

### 📌 Prerequisites

1. A 16GB or larger USB drive
2. A Mac or Hackintosh for creating installation media
3. Download macOS installer

### 🔧 Installation Steps

#### 1️⃣ Prepare EFI Partition

```bash
# Format USB as GPT partition
# Create FAT32 partition with volume name EFI
```

#### 2️⃣ Copy EFI Files

Copy the `EFI` folder from this project to the USB's ESP partition

#### 3️⃣ Configure BIOS Settings

| Setting | Recommended Value |
|---------|-------------------|
| Fast Boot | Disabled |
| Secure Boot | Disabled |
| CSM Compatibility | Disabled |
| XHCI Hand-off | Enabled |
| Above 4G Decoding | Enabled |
| Resizable BAR | Enabled (if supported) |

#### 4️⃣ Boot Installation

1. Insert USB and boot
2. Select `Install macOS` from OpenCore menu
3. Format target disk as APFS in Disk Utility
4. Select `Install macOS` to begin installation

#### 5️⃣ Post-Installation

After first boot, run [OpenCore Configurator](https://mackie100projects.altervista.org/download-opencore-configurator/) or [ProperTree](https://github.com/corpnewt/ProperTree) to validate configuration

---

## 📝 Kext Update Log

### v1.0.8 MOD (2025-04-30)

<p align="center">
  <img src="https://img.shields.io/badge/Date-2025--04--30-blue?style=flat-square" alt="Date">
  <img src="https://img.shields.io/badge/OpenCore-1.0.8%20MOD-green?style=flat-square" alt="OpenCore">
</p>

#### ✨ Core Updates

- OpenCore upgraded to 1.0.8 MOD
- All kernel extensions (kext) updated to latest stable versions
- Added HFS+ filesystem support (hfsplus.efi)
- Custom AMD Radeon Pro W6600X GPU configuration
- IOSkywalkFamily.kext upgraded to v1.2.0
- **macOS 26.5 Tahoe native support added**
- Added BlueToolFixup.kext Bluetooth support
- Optimized boot-args compatibility parameters

### v1.0.1 MOD (2024-09-05)

- OpenCore updated to 1.0.1 MOD
- HFS+ filesystem support added
- AMD Radeon Pro W6600 custom configuration
- IOSkywalkFamily.kext v1.1.0

### v0.9.8a (2024-02-09)

- OpenCore updated to 0.9.8 official
- IGPU version updated to OC 1.01 MOD

---

## 📶 Broadcom WiFi Driver Guide

For macOS Sonoma/Sequoia/Tahoe

### 🔧 Using OpenCore Legacy Patcher

<p align="center">
  <a href="https://github.com/dortania/OpenCore-Legacy-Patcher"><img src="https://img.shields.io/badge/Download-OCLP-red?style=for-the-badge" alt="Download OCLP"></a>
</p>

#### 📋 Procedure

1. **Launch Tool**
   - Run OpenCore Legacy Patcher application

2. **Apply Network Driver Patch**
   - Double-click `Post-Install Root Patch` module
   - Select from patch list:
     - ✅ `Networking: Modern Wireless` (Recommended)
     - ✅ `Networking: Legacy Wireless` (Legacy devices)

3. **Execute System Modification**
   - Click `Start Root Patching` to begin patch process
   - Select `Yes` in privilege confirmation dialog

4. **Finalize Installation**
   - Wait for completion (approx. 1-3 minutes)
   - Click `Reboot` to restart and apply changes

> 💡 **Tip**: Re-apply patches after system updates for optimal compatibility

---

## ❓ FAQ

### Q1: Broadcom WiFi not working?

**A**: Make sure to run OpenCore Legacy Patcher's Post-Install Root Patch

### Q2: iGPU not working?

**A**: Current `ig-platform-id` is `00003BE9`, check `igfxfw=2` in `boot-args` if issues occur

### Q3: Stuck during installation?

**A**: Refer to [dortania/Hackintosh Vanilla Desktop Guide](https://github.com/dortania/OpenCore-Install-Guide) for detailed troubleshooting

### Q4: How to keep WiFi working after system update?

**A**: Re-run OCLP's Root Patch after major system version updates

---

## 📜 License

<p align="center">
  <img src="https://img.shields.io/badge/License-MIT-blue?style=for-the-badge" alt="MIT License">
</p>

```
MIT License

Copyright (c) 2023-2025 jhihhe

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

## 🤝 Contributing

Issues and Pull Requests are welcome!

### Submitting Issues

- Please describe specific hardware configuration and macOS version
- Provide error logs (if any)
- Explain reproduction steps

### Submitting PR

1. Fork this repository
2. Create new branch (`git checkout -b feature/amazing-feature`)
3. Commit changes (`git commit -m 'Add amazing feature'`)
4. Push to branch (`git push origin feature/amazing-feature`)
5. Create Pull Request

---

## 🙏 Acknowledgements

- [OpenCore](https://github.com/acidanthera/OpenCorePkg) - Open source EFI bootloader
- [Acidanthera](https://github.com/acidanthera) - Developers of all drivers and patches
- [Dortania](https://github.com/dortania) - Hackintosh community contributors
- [OpenCore Legacy Patcher](https://github.com/dortania/OpenCore-Legacy-Patcher) - Legacy hardware support tool

---

<p align="center">
  <img src="https://img.shields.io/badge/Made%20with-❤️-red?style=for-the-badge" alt="Made with Love">
  <img src="https://img.shields.io/badge/Powered%20by-Hackintosh-blue?style=for-the-badge" alt="Powered by Hackintosh">
</p>

<p align="center">
  <strong>If you find this project helpful, please ⭐ Star to show support!</strong>
</p>

---

## 🔗 Related Links

| Resource | Link |
|----------|------|
| GitHub Repository | https://github.com/jhihhe/Asus-Prime-Z390P-i9-9900K-UHD630-RX-6600XT-Hackintosh |
| OpenCore Documentation | https://dortania.github.io/OpenCore-Install-Guide/ |
| Dortania Community | https://github.com/dortania/OpenCore-Legacy-Patcher |
| AMD GPU Fix | https://github.com/acidanthera/WhateverGreen |
| Audio Driver | https://github.com/acidanthera/AppleALC |

---

*Last updated: 2025-04-30 | OpenCore 1.0.8 MOD | macOS 26.5 Tahoe Support*
