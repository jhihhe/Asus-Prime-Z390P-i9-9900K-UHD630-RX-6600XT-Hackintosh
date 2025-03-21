<p align="center">
  <img src="https://img.shields.io/badge/OpenCore-1.0.5_MOD-9cf?style=flat-square&logo=apple" />    
  <img src="https://img.shields.io/badge/macOS-Sequoia_15.4-success?style=flat-square&logo=apple" />    
  <img src="https://img.shields.io/badge/Platform-Windows%20%7C%20macOS%20%7C%20Linux-green" />      

</p>

# 🍎 Asus Prime Z390-P Hackintosh Configuration Guide

![Hackintosh Screenshot](https://i.postimg.cc/yYVcNt5H/i-Shot-2022-07-01-09-57-21.png)

[中文](https://github.com/jhihhe/Asus-Prime-Z390P-i9-9900K-UHD630-RX-6600XT-Hackintosh/blob/main/README.md) | [English](https://github.com/jhihhe/Asus-Prime-Z390P-i9-9900K-UHD630-RX-6600XT-Hackintosh/blob/main/README-EN.md)

## 📥 Download Guide
[![Release](https://img.shields.io/badge/Download-Releases-blue?style=for-the-badge&logo=github)](https://github.com/jhihhe/Asus-Prime-Z390P-i9-9900K-UHD630-RX-6600XT-Hackintosh/releases)

> 💡 Notes:  
> - For iGPU-only setups, download the **IGPU Version**  
> - Required manual configurations:  
>   `Board Serial Number` | `Serial Number` | `SmUUID`  
>   ➤ Modify "Custom UUID" in `SysParameter`  
>   ➤ Update `MLB` and `ROM` in `RtVariables`

---

## 🚀 Changelog
  - ✅ OpenCore upgraded to 1.0.5 MOD  
  - ✅ All Kexts updated to latest versions
  - ✅ Added hfsplus.efi for USB installation support

---

## ⚙️ Hardware Specifications
| Component       | Model                                      |
|-----------------|-------------------------------------------|
| Motherboard     | ASUS PRIME Z390-P (BIOS 3006) [Download](https://www.asus.com/us/motherboards-components/motherboards/prime/prime-z390-p/HelpDesk_BIOS/) |
| CPU             | Intel Core i9-9900K                       |
| Cooler          | THERMALRIGHT Frost Commander 140 BLACK    |
| iGPU            | Intel UHD 630 (Use IGPU Version)          |
| dGPU            | AMD Radeon RX 6600 XT                     |
| LAN             | Realtek RTL8111H Gigabit Ethernet         |
| WiFi/BT         | BCM943602CS (BT4.2)                       |
| Audio           | Realtek ALC 887                           |
| Storage         | WD SN750 500GB (TRIM Enabled)             |

![Storage Info](https://tva1.sinaimg.cn/large/cec1774cly8h057sy9inrj21860u0tcy.jpg)

---

## ⚡ BIOS Settings
1. **Advanced** → **CPU Configuration**  
   - Intel(VMX) Virtualization Technology → **Enabled**

2. **Advanced** → **System Agent (SA) Configuration**  
   - Primary Display → **Auto**  
   - iGPU → **Enabled**  
   - DVMT Pre-Allocated → **1024M**  
   - RC6 → **Auto**

3. **Advanced** → **USB Configuration**  
   - XHCI Hand-off → **Enabled**

4. **Boot** → **Boot Configuration**  
   - Fast Boot → **Disabled**  
   - Wait For F1 Error → **Disabled**

---

## 🍏 System Compatibility
**Supported OS**: macOS Catalina ~ macOS Sequoia
**OpenCore**: 1.0.5

![Theme Preview](https://tva2.sinaimg.cn/large/cec1774cly8h1g75kzm0vj21hc0u0gmt.jpg)

---

## ✅ Functional Verification
| Feature            | Status | Details |
|--------------------|--------|---------|
| CPU Power Management | ✔️   | [Screenshot](https://tva4.sinaimg.cn/large/cec1774cly8h057spanbgj21860u0dio.jpg) |
| iGPU/dGPU Acceleration | ✔️ | HIDPI/H.264/HEVC support |
| Audio Output       | ✔️   | 3.5mm Jack working |
| USB 3.0            | ✔️   | Requires USBPorts.kext customization |
| Wired Network      | ✔️   | RealtekRTL8111.kext |
| WiFi & Bluetooth   | ✔️   | BCM943602CS fully functional |
| Sleep/Wake         | ✔️   | S3 Sleep supported |
| Apple Services     | ✔️   | iCloud/iMessage fully functional |

---

## 📝 Usage Tips
1. **SMBIOS Settings**: Default `iMac19,1` (Modify post-installation)
2. **Verbose Mode**: Add `-v` to `boot-args`
3. **Multi-Boot Support**: ScanPolicy=0 for Windows/Linux
4. **USB Configuration**:
   - Disable USBPorts.kext on macOS 11.3+
   - Set `XhciPortLimit=true`

---

## 🙏 Acknowledgments
This project references configurations from [igarashikenshin](https://github.com/igarashikenshin/Hackintosh-Asus-Prime-Z390P_i9-9900K_RX6800XT). Special thanks to the Hackintosh community for their contributions!
