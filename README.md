# *Hackintosh-Asus_Prime_Z390P-i9-9900K_UHD630&6600XT-EFI_OpenCore-0.7.9 macOS*

# [中文](https://github.com/jhihhe/Hackintosh-Asus_Prime_Z390P-i9-9900K_UHD630-EFI_OpenCore-0.7.9-macOS/blob/main/README.md)｜[English](https://github.com/jhihhe/Hackintosh-Asus_Prime_Z390P-i9-9900K_UHD630-EFI_OpenCore-0.7.9-macOS/blob/main/README-EN.md)

# 下载点击[releases](https://github.com/jhihhe/Hackintosh-Asus_Prime_Z390P-i9-9900K_UHD630-RX-6600XT-EFI_OpenCore-0.7.9-macOS/releases)

# 请自行生成Board Serial Number、序列号、SmUUID，并相应的修改SysPrameter系统参数中的“自定义UUID”，和RtVariables变量设置中的MLB、ROM

![系统信息](https://tva1.sinaimg.cn/large/cec1774cly8h02ktqf6n1j20yk0lidhq.jpg)

### 配置
1. 主板: ASUS PRIME Z390-P （BIOS Version 3006 请点击这里[下载BIOS](https://www.asus.com/us/motherboards-components/motherboards/prime/prime-z390-p/HelpDesk_BIOS/) ）
1. CPU: Intel® Core™ i9-9900K Processor
1. 核显: Intel® UHD Graphics 630(仅使用核显请下载版本号小与220305的版本)
1. 显卡: AMD Radeon RX 6600 XT
1. 板载网卡: Realtek® RTL8111H Gigabit LAN Controller
1. WiFi/蓝牙: BCM943602CS（BT4.2）
1. 声卡: Realtek® ALC 887 8-Channel High Definition Audio
1. 固态硬盘: 西数SN750 500GB
![硬盘信息](https://tva1.sinaimg.cn/large/cec1774cly8h02l03yyq9j21860u0ae3.jpg)

### BIOS设置
1. 高级-CPU设置--Intel(VMX) Virtualization Technology -enable
1. 高级-北桥-显示设置--首选显卡-Auto，初始化IGPU-enable，DVMT Pre-Allocated-1024M，RC6-auto
1. 高级-USB Configuration--XHCI Hand-off -enable
1. 高级-内置设备-Serial Port Configuration-Serial Port -off
1. 启动-启动设置--快速启动-disable，若出现错误等待按下F1键-disable
1. 设置模式-高级模式

# **可适用操作系统版本：macOS Catalina 10.15.1～Big Sur 11.6.5/支持macOS Monterey 12.3 Beta5**
1. OpenCore版本：0.7.9（内含主题如下图） 
![主题](https://i.loli.net/2021/09/11/t4FBZPeHkwdufiG.png)
![主题](https://i.loli.net/2021/07/31/uFHJD2BMazqmTcA.png)
1. CPU变频：正常。 
![CPU](https://tva1.sinaimg.cn/large/cec1774cly8gzplake51qj208m0hnjs2.jpg)
![内存](https://tva2.sinaimg.cn/large/cec1774cly8h02l3ltb6tj21860u0q6j.jpg)
1. UHD630：正常，VRAM动态，最大值：4095 MB，开启HIDPI，开启H.264&HEVC硬件解码加速 
![显卡](https://tva3.sinaimg.cn/large/cec1774cly8h02kyt7wtaj21860u0q62.jpg) 
![硬件解码加速：H.264&HEVC解码](https://tva3.sinaimg.cn/large/cec1774cly8gzz45wjjlrj21880u0tc6.jpg)
1. 3.5mm声音
![声卡](https://tva2.sinaimg.cn/large/cec1774cly8h02l3k77ozj21860u0ad8.jpg)
1. USB：正常，Big Sur 11.3版本后，如USB加载不正常，需自行定制usb，或取消加载USBport.kext，将XhciPortLimit值变更为true 
![USB](https://tva2.sinaimg.cn/large/cec1774cly8h02l3obe9aj21860u0tcc.jpg)
1. 有线网卡：正常，使用了RealtekRTL8111.kext 
![有线网卡](https://tva3.sinaimg.cn/large/cec1774cly8h02l3es8a9j21860u0q5l.jpg)
1. 无线网卡：正常 
![Wi-Fi](https://tva1.sinaimg.cn/large/cec1774cly8h02l3scsepj21860u0n1j.jpg)
1. 睡眠唤醒：正常 
![睡眠](https://tva3.sinaimg.cn/large/cec1774cly8h02l5ioja1j212p0u0di8.jpg)
1. 关机开机：正常
1. iCloud & App Store & iMessage & FaceTime：正常
1. AirDrop & HandOff & Continuity：正常。
![蓝牙](https://tva2.sinaimg.cn/large/cec1774cly8h02l3i58prj21860u00wc.jpg)

### Tips：

1. 机型需设定为iMAC19.1（现已预置，安装完成后请自行修改）。
1. 该config默认为无verbose模式。如需启用verbose模式，config.plist需要修改以下一项：NVRAM-Add-7C436110-AB2A-4BBB-A880-FE41995C9F82-boot-args，添加-v。
1. 该config启动盘策略 ScanPolicy 值设置为0。可引导Windows或Other OS（Linux、Unix）如需指定搜索分区类型，可参考OC配置手册。

# 鸣谢 
# 采用了igarashikenshin的README.md编辑格式，如果需其他版本可点击大佬链接查看
https://github.com/igarashikenshin/Hackintosh-Asus-Prime-Z390P_i9-9900K_RX6800XT
