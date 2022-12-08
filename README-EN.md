# *Hackintosh-Asus_Prime_Z390P-i9-9900K_UHD630&6600XT-EFI_OpenCore-0.8.7 macOS*

# [中文](https://github.com/jhihhe/Hackintosh-Asus_Prime_Z390P-i9-9900K_UHD630-RX-6600XT-EFI_OpenCore-0.8.7-macOS/blob/main/README.md)｜[English](https://github.com/jhihhe/Hackintosh-Asus_Prime_Z390P-i9-9900K_UHD630-RX-6600XT-EFI_OpenCore-0.8.7-macOS/blob/main/README-EN.md)

# Download click [releases](https://github.com/jhihhe/Hackintosh-Asus_Prime_Z390P-i9-9900K_UHD630-RX-6600XT-EFI_OpenCore-0.8.7-macOS/releases)
Please download the IGPU version or the version with the version number less than 220305 if you only use the nuclear display
# Please generate the Board Serial Number, serial number, SmUUID by yourself, and modify the "custom UUID" in the SysPrameter system parameters, and the MLB and ROM in the RtVariables variable settings accordingly.

![System Information](https://i.postimg.cc/cLKjSQZq/i-Shot-2022-06-30-22-31-28.png)
![System Information 2](https://i.postimg.cc/BZgRcSNz/i-Shot-2022-06-30-22-31-44.png)

## Changelog:
- [x] 1. Update oc version to 0.8.7/1208version
- [x] 2. Update all kext kernel extension drivers to the latest version
- [x] 3. Add hfsplus.efi to support U disk installation

## If you only use nuclear display, please download the IGPU version

## configure
1. Motherboard: ASUS PRIME Z390-P (BIOS Version 3006 please click here [Download BIOS](https://www.asus.com/us/motherboards-components/motherboards/prime/prime-z390-p/HelpDesk_BIOS/) )
1. CPU: Intel® Core™ i9-9900K Processor
1. CPU cooling: THERMALRIGHT Frost Commander 140 BLACK
1. Core Graphics: Intel® UHD Graphics 630 (For core graphics only, please download the IGPU version or the version with the version number less than 220305)
1. Graphics Card: AMD Radeon RX 6600 XT
1. Onboard LAN: Realtek® RTL8111H Gigabit LAN Controller
1. WiFi/Bluetooth: BCM943602CS (BT4.2)
1. Sound Card: Realtek® ALC 887 8-Channel High Definition Audio
1. Solid State Drive: Western Digital SN750 500GB (with TRIM enabled)
![HDD Information](https://tva1.sinaimg.cn/large/cec1774cly8h057sy9inrj21860u0tcy.jpg)

### BIOS settings
1. Advanced-CPU Settings--Intel(VMX) Virtualization Technology-enable
1. Advanced - North Bridge - Display Settings - Preferred Graphics Card - Auto, Initialize IGPU-enable, DVMT Pre-Allocated-1024M, RC6-auto
1. Advanced-USB Configuration--XHCI Hand-off -enable
1. Advanced-Built-in Device-Serial Port Configuration-Serial Port-off
1. Start - Startup Settings - Quick Start - disable, if an error occurs, wait for pressing the F1 key - disable
1. Setup Mode - Advanced Mode

# **Applicable OS version: macOS Catalina 10.15.1～Big Sur 11.6.6/supports macOS Monterey 12.6.1/macOS Ventura 13.1**
1. OpenCore version: 0.8.7 
![Theme](https://tva2.sinaimg.cn/large/cec1774cly8h1g75kzm0vj21hc0u0gmt.jpg)
![Theme](https://i.postimg.cc/yYVcNt5H/i-Shot-2022-07-01-09-57-21.png)
- [x] 1. CPU frequency conversion: works fine.
![CPU](https://tva4.sinaimg.cn/large/cec1774cly8h057spanbgj21860u0dio.jpg)
![Memory](https://tva2.sinaimg.cn/large/cec1774cly8h057svhmylj21860u0n0u.jpg)
- [x] 2. UHD630: works normally, VRAM is dynamic, maximum value: 4095 MB, HIDPI is enabled, H.264&HEVC hardware decoding acceleration is enabled, RX6600XT: works normally, add independent display AAPL, slot-name parameters, add RadeonSensor.kext&SMCRadeonGPU .kext to display discrete graphics temperature as normal
![Graphics Card](https://tva4.sinaimg.cn/large/cec1774cly8h1xkrsg9spj21eg0u00vz.jpg)
![Graphics card 2](https://tva2.sinaimg.cn/large/cec1774cly8h1xkmoixcpj20lq0tg0uz.jpg)
![Hardware decoding acceleration: H.264&HEVC decoding](https://tva3.sinaimg.cn/large/cec1774cly8h1xkojr9ugj21880u0421.jpg)
- [x] 3. 3.5mm sound: works fine
![Sound Card](https://tva3.sinaimg.cn/large/cec1774cly8h057stfz6fj21860u0gov.jpg)
- [x] 4. USB: Works normally, after Big Sur 11.3 version, if the USB is not loaded properly, you need to customize the USB, or cancel the loading of USBport.kext, and change the XhciPortLimit value to true
![USB](https://pic.imgdb.cn/item/62280dc95baa1a80abdfa1ee.png)
- [x] 5. Wired network card: works fine, using RealtekRTL8111.kext
![Wired network card](https://pic.imgdb.cn/item/62280dc95baa1a80abdfa1f6.png)
- [x] 6. Wireless card: works fine
![Wi-Fi](https://pic.imgdb.cn/item/62280dd25baa1a80abdfa953.png)
- [x] 7. Sleep wake: works fine
![Sleep 2](https://tva2.sinaimg.cn/large/cec1774cly8h057snf0lzj21860u0wh5.jpg)
![Sleep](https://tva1.sinaimg.cn/large/cec1774cly8h057wpxhe1j212p0u0410.jpg)
- [x] 8. Power off: Works fine
- [x] 9. iCloud & App Store & iMessage & FaceTime: OK
- [x] 10. AirDrop & HandOff & Continuity: OK.
![Bluetooth](https://pic.imgdb.cn/item/62280dcf5baa1a80abdfa682.png)

###Tips:

1. The model needs to be set to iMAC19.1 (it is already preset, please modify it after the installation is complete).
1. The config defaults to no verbose mode. To enable verbose mode, config.plist needs to modify the following one: NVRAM-Add-7C436110-AB2A-4BBB-A880-FE41995C9F82-boot-args, add -v.
1. The config startup disk policy ScanPolicy value is set to 0. Bootable Windows or Other OS (Linux, Unix) To specify the search partition type, please refer to the OC configuration manual.

# thanks
# Using igarashikenshin's README.md editing format, if you need other versions, you can click the link to view
https://github.com/igarashikenshin/Hackintosh-Asus-Prime-Z390P_i9-9900K_RX6800XT
