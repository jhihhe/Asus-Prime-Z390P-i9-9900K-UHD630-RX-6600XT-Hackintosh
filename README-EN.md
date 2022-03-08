# *Hackintosh-Asus_Prime_Z390P-i9-9900K_UHD630&6600XT-EFI_OpenCore-0.7.9 macOS*

# [Chinese](https://github.com/jhihhe/Hackintosh-Asus_Prime_Z390P-i9-9900K_UHD630-EFI_OpenCore-0.7.9-macOS/blob/main/README.md)｜[English](https://github.com/jhihhe/Hackintosh-Asus_Prime_Z390P-i9-9900K_UHD630-EFI_OpenCore-0.7.9-macOS/blob/main/README-EN.md)

# Download click [releases](https://github.com/jhihhe/Hackintosh-Asus_Prime_Z390P-i9-9900K_UHD630-RX-6600XT-EFI_OpenCore-0.7.9-macOS/releases)

# Please generate the Board Serial Number, serial number, SmUUID by yourself, and modify the "custom UUID" in the SysPrameter system parameters, and the MLB and ROM in the RtVariables variable settings accordingly.

![System Information](https://tva1.sinaimg.cn/large/cec1774cly8h02ktqf6n1j20yk0lidhq.jpg)

### Configuration
1. Motherboard: ASUS PRIME Z390-P (BIOS Version 3006 please click here [Download BIOS](https://www.asus.com/us/motherboards-components/motherboards/prime/prime-z390-p/HelpDesk_BIOS/) )
1. CPU: Intel® Core™ i9-9900K Processor
1. Core Graphics: Intel® UHD Graphics 630 (For core graphics only, please download the version with the smaller version number and 220305)
1. Graphics Card: AMD Radeon RX 6600 XT
1. Onboard LAN: Realtek® RTL8111H Gigabit LAN Controller
1. WiFi/Bluetooth: BCM943602CS (BT4.2)
1. Sound Card: Realtek® ALC 887 8-Channel High Definition Audio
1. Solid State Drive: Western Digital SN750 500GB
![HDD Information](https://tva1.sinaimg.cn/large/cec1774cly8h02l03yyq9j21860u0ae3.jpg)

### BIOS settings
1. Advanced-CPU Settings--Intel(VMX) Virtualization Technology-enable
1. Advanced - North Bridge - Display Settings - Preferred Graphics Card - Auto, Initialize IGPU-enable, DVMT Pre-Allocated-1024M, RC6-auto
1. Advanced-USB Configuration--XHCI Hand-off -enable
1. Advanced-Built-in Device-Serial Port Configuration-Serial Port-off
1. Start - Startup Settings - Quick Start - disable, if an error occurs, wait for pressing the F1 key - disable
1. Setup Mode - Advanced Mode

# **Applicable OS version: macOS Catalina 10.15.1～Big Sur 11.6.5/support macOS Monterey 12.3 Beta5**
1. OpenCore version: 0.7.9 (with themes as shown below)
![Theme](https://i.loli.net/2021/09/11/t4FBZPeHkwdufiG.png)
![Theme](https://i.loli.net/2021/07/31/uFHJD2BMazqmTcA.png)
1. CPU frequency conversion: normal.
![CPU](https://tva1.sinaimg.cn/large/cec1774cly8gzplake51qj208m0hnjs2.jpg)
![Memory](https://tva2.sinaimg.cn/large/cec1774cly8h02l3ltb6tj21860u0q6j.jpg)
1. UHD630: normal, VRAM dynamic, maximum: 4095 MB, enable HIDPI, enable H.264&HEVC hardware decoding acceleration
![Graphics Card](https://tva3.sinaimg.cn/large/cec1774cly8h02kyt7wtaj21860u0q62.jpg)
![Hardware decoding acceleration: H.264&HEVC decoding](https://tva3.sinaimg.cn/large/cec1774cly8gzz45wjjlrj21880u0tc6.jpg)
1. 3.5mm sound
![Sound Card](https://tva2.sinaimg.cn/large/cec1774cly8h02l3k77ozj21860u0ad8.jpg)
1. USB: Normal, after Big Sur 11.3 version, if the USB loading is abnormal, you need to customize the USB, or cancel the loading of USBport.kext, and change the XhciPortLimit value to true
![USB](https://tva2.sinaimg.cn/large/cec1774cly8h02l3obe9aj21860u0tcc.jpg)
1. Wired network card: normal, using RealtekRTL8111.kext
![Wired network card](https://tva3.sinaimg.cn/large/cec1774cly8h02l3es8a9j21860u0q5l.jpg)
1. Wireless network card: normal
![Wi-Fi](https://tva1.sinaimg.cn/large/cec1774cly8h02l3scsepj21860u0n1j.jpg)
1. Sleep wake up: normal
![Sleep](https://tva3.sinaimg.cn/large/cec1774cly8h02l5ioja1j212p0u0di8.jpg)
1. Power off and on: normal
1. iCloud & App Store & iMessage & FaceTime: Normal
1. AirDrop & HandOff & Continuity: Normal.
![Bluetooth](https://tva2.sinaimg.cn/large/cec1774cly8h02l3i58prj21860u00wc.jpg)

###Tips:

1. The model needs to be set to iMAC19.1 (it is already preset, please modify it after the installation is complete).
1. The config defaults to no verbose mode. To enable verbose mode, config.plist needs to modify the following one: NVRAM-Add-7C436110-AB2A-4BBB-A880-FE41995C9F82-boot-args, add -v.
1. The config startup disk policy ScanPolicy value is set to 0. Bootable Windows or Other OS (Linux, Unix) To specify the search partition type, please refer to the OC configuration manual.

# thanks
# Using igarashikenshin's README.md editing format, if you need other versions, you can click the link to view
https://github.com/igarashikenshin/Hackintosh-Asus-Prime-Z390P_i9-9900K_RX6800XT
