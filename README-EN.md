# *Hackintosh-Asus_Prime_Z390P-i9-9900K_UHD630&6600XT-EFI_OpenCore-0.8.1 macOS*

# [Chinese](https://github.com/jhihhe/Hackintosh-Asus_Prime_Z390P-i9-9900K_UHD630-RX-6600XT-EFI_OpenCore-0.8.1-macOS/blob/main/README.md)｜[English](https://github.com/jhihhe/Hackintosh-Asus_Prime_Z390P-i9-9900K_UHD630-RX-6600XT-EFI_OpenCore-0.8.1-macOS/blob/main/README-EN.md)

# Download click [releases](https://github.com/jhihhe/Hackintosh-Asus_Prime_Z390P-i9-9900K_UHD630-RX-6600XT-EFI_OpenCore-0.8.1-macOS/releases)
Please download the IGPU version or the version with the version number less than 220305 if you only use the 630 display
# Please generate the Board Serial Number, serial number, SmUUID by yourself, and modify the "custom UUID" in the SysPrameter system parameters, and the MLB and ROM in the RtVariables variable settings accordingly.

![系统信息](https://static01.imgkr.com/temp/0afe2bbe865d4788bc42c6afc025f601.png)
![系统信息2](https://tva2.sinaimg.cn/large/cec1774cly8h274zgu9rsj20te0hi42o.jpg)

## Changelogs：
- [x] 1. Update oc version to 0.8.1/0513 compiled version
- [x] 2. Update all kext kernel extension drivers to the latest version
- [x] 3. Add hfsplus.efi to support USB flash disk installation 
- [x] 4. Add any AMD graphics card support version, theoretically support 5x0, 5x00, 6x00 graphics cards
## If you use the Core display card UHD630 only, please download the IGPU version

### Configuration
1. Motherboard: ASUS PRIME Z390-P (BIOS Version 3006 please click here [Download BIOS](https://www.asus.com/us/motherboards-components/motherboards/prime/prime-z390-p/HelpDesk_BIOS/) )
1. CPU: Intel® Core™ i9-9900K Processor
1. CPU Cooler：THERMALRIGHT Frost Commander 140 BLACK
1. Core Graphics: Intel® UHD Graphics 630 (Please download the IGPU version or the version with the version number less than 220305 if you only use the nuclear display)
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

# **Applicable OS version: macOS Catalina 10.15.1～Big Sur 11.6.5/support macOS Monterey 12.4 beta4**
1. OpenCore version: 0.8.1 (with themes as shown below)
![Theme](https://tva2.sinaimg.cn/large/cec1774cly8h1g75kzm0vj21hc0u0gmt.jpg)
![Theme](https://i.loli.net/2021/07/31/uFHJD2BMazqmTcA.png)
1. CPU frequency conversion: works fine.
![CPU](https://tva4.sinaimg.cn/large/cec1774cly8h057spanbgj21860u0dio.jpg)
![Memory](https://tva2.sinaimg.cn/large/cec1774cly8h057svhmylj21860u0n0u.jpg)
1. UHD630: works fine, VRAM is dynamic, maximum value: 4095 MB, HIDPI is enabled, H.264&HEVC hardware decoding acceleration is enabled, RX6600XT: works fine, increase the independent display AAPL, slot-name parameters, add RadeonSensor.kext&SMCRadeonGPU.kext, to Normal display of discrete graphics card temperature
![Graphics Card](https://tva4.sinaimg.cn/large/cec1774cly8h1xkrsg9spj21eg0u00vz.jpg)
![Graphics card 2](https://tva2.sinaimg.cn/large/cec1774cly8h1xkmoixcpj20lq0tg0uz.jpg)
![Hardware decoding acceleration: H.264&HEVC decoding](https://tva3.sinaimg.cn/large/cec1774cly8h1xkojr9ugj21880u0421.jpg)
1. 3.5mm sound: works fine
![Sound Card](https://tva3.sinaimg.cn/large/cec1774cly8h057stfz6fj21860u0gov.jpg)
1. USB: works fine. After Big Sur version 11.3, if the USB is not loaded properly, you need to customize the USB, or cancel the loading of USBport.kext, and change the XhciPortLimit value to true
![USB](https://pic.imgdb.cn/item/62280dc95baa1a80abdfa1ee.png)
1. Wired network card: works fine, using RealtekRTL8111.kext
![Wired network card](https://pic.imgdb.cn/item/62280dc95baa1a80abdfa1f6.png)
1. Wireless network card: works fine
![Wi-Fi](https://pic.imgdb.cn/item/62280dd25baa1a80abdfa953.png)
1. Sleep wake: works fine
![Sleep 2](https://tva2.sinaimg.cn/large/cec1774cly8h057snf0lzj21860u0wh5.jpg)
![Sleep](https://tva1.sinaimg.cn/large/cec1774cly8h057wpxhe1j212p0u0410.jpg)
1. Power off and on: Works fine
1. iCloud & App Store & iMessage & FaceTime: works fine
1. AirDrop & HandOff & Continuity: works fine.
![Bluetooth](https://pic.imgdb.cn/item/62280dcf5baa1a80abdfa682.png)

###Tips:

1. The model needs to be set to iMAC19.1 (it is already preset, please modify it after the installation is complete).
1. The config defaults to no verbose mode. To enable verbose mode, config.plist needs to modify the following one: NVRAM-Add-7C436110-AB2A-4BBB-A880-FE41995C9F82-boot-args, add -v.
1. The config startup disk policy ScanPolicy value is set to 0. Bootable Windows or Other OS (Linux, Unix) To specify the search partition type, please refer to the OC configuration manual.

# thanks
# Using igarashikenshin's README.md editing format, if you need other versions, you can click the link to view
https://github.com/igarashikenshin/Hackintosh-Asus-Prime-Z390P_i9-9900K_RX6800XT
