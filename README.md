# *Asus-Prime-Z390P i9 9900K UHD630/RX-6600XT-Hackintosh*

# [中文](https://github.com/jhihhe/Asus-Prime-Z390P-i9-9900K-UHD630-RX-6600XT-Hackintosh/blob/main/README.md)｜[English](https://github.com/jhihhe/Asus-Prime-Z390P-i9-9900K-UHD630-RX-6600XT-Hackintosh/blob/main/README-EN.md)

# 下载点击[releases](https://github.com/jhihhe/Asus-Prime-Z390P-i9-9900K-UHD630-RX-6600XT-Hackintosh/releases)
仅使用核显请下载IGPU版本
# 请自行生成Board Serial Number、序列号、SmUUID，并相应的修改SysPrameter系统参数中的“自定义UUID”，和RtVariables变量设置中的MLB、ROM

## 更新日志：
- [x] 1. 更新 oc 版本到1.0.1 MOD版
- [x] 2. 更新所有kext内核拓展驱动到最新版本
- [x] 3. 添加hfsplus.efi以支持u盘安装

## 如仅使用核显请下载IGPU版本

## 配置
1. 主板: ASUS PRIME Z390-P （BIOS Version 3006 请点击这里[下载BIOS](https://www.asus.com/us/motherboards-components/motherboards/prime/prime-z390-p/HelpDesk_BIOS/) ）
1. CPU: Intel® Core™ i9-9900K Processor
1. CPU 散热：THERMALRIGHT Frost Commander 140 BLACK
1. 核显: Intel® UHD Graphics 630(仅使用核显请下载IGPU版本或版本号小于220305的版本)
1. 显卡: AMD Radeon RX 6600 XT
1. 板载网卡: Realtek® RTL8111H Gigabit LAN Controller
1. WiFi/蓝牙: BCM943602CS（BT4.2）
1. 声卡: Realtek® ALC 887 8-Channel High Definition Audio
1. 固态硬盘: 西数SN750 500GB（开启TRIM）
![硬盘信息](https://tva1.sinaimg.cn/large/cec1774cly8h057sy9inrj21860u0tcy.jpg)

### BIOS设置
1. 高级-CPU设置--Intel(VMX) Virtualization Technology -enable
1. 高级-北桥-显示设置--首选显卡-Auto，初始化IGPU-enable，DVMT Pre-Allocated-1024M，RC6-auto
1. 高级-USB Configuration--XHCI Hand-off -enable
1. 高级-内置设备-Serial Port Configuration-Serial Port -off
1. 启动-启动设置--快速启动-disable，若出现错误等待按下F1键-disable
1. 设置模式-高级模式

# **可适用操作系统版本：支持macOS Catalina/Big Sur/macOS Monterey/macOS Ventura/macOS Sonoma **
1. OpenCore版本：1.0.1
![主题](https://tva2.sinaimg.cn/large/cec1774cly8h1g75kzm0vj21hc0u0gmt.jpg)
![主题](https://i.postimg.cc/yYVcNt5H/i-Shot-2022-07-01-09-57-21.png)
- [x] 1. CPU变频：工作正常。 
![CPU](https://tva4.sinaimg.cn/large/cec1774cly8h057spanbgj21860u0dio.jpg)
![内存](https://tva2.sinaimg.cn/large/cec1774cly8h057svhmylj21860u0n0u.jpg)
- [x] 2. UHD630：工作正常，VRAM动态，最大值：4095 MB，开启HIDPI，开启H.264&HEVC硬件解码加速，RX6600XT：工作正常，增加独显AAPL,slot-name参数，加入RadeonSensor.kext&SMCRadeonGPU.kext，以正常显示独立显卡温度
![显卡](https://tva4.sinaimg.cn/large/cec1774cly8h1xkrsg9spj21eg0u00vz.jpg)
![显卡2](https://tva2.sinaimg.cn/large/cec1774cly8h1xkmoixcpj20lq0tg0uz.jpg)
![硬件解码加速：H.264&HEVC解码](https://tva3.sinaimg.cn/large/cec1774cly8h1xkojr9ugj21880u0421.jpg)
- [x] 3. 3.5mm声音：工作正常
![声卡](https://tva3.sinaimg.cn/large/cec1774cly8h057stfz6fj21860u0gov.jpg)
- [x] 4. USB：工作正常，Big Sur 11.3版本后，如USB加载不正常，需自行定制usb，或取消加载USBport.kext，将XhciPortLimit值变更为true 
- [x] 5. 有线网卡：工作正常，使用了RealtekRTL8111.kext 
- [x] 6. 无线网卡：工作正常 
- [x] 7. 睡眠唤醒：工作正常 
- [x] 8. 关机开机：工作正常
- [x] 9. iCloud & App Store & iMessage & FaceTime：正常
- [x] 10. AirDrop & HandOff & Continuity：正常。

### Tips：

1. 机型需设定为iMAC19.1（现已预置，安装完成后请自行修改）。
1. 该config默认为无verbose模式。如需启用verbose模式，config.plist需要修改以下一项：NVRAM-Add-7C436110-AB2A-4BBB-A880-FE41995C9F82-boot-args，添加-v。
1. 该config启动盘策略 ScanPolicy 值设置为0。可引导Windows或Other OS（Linux、Unix）如需指定搜索分区类型，可参考OC配置手册。

# 鸣谢 
# 采用了igarashikenshin的README.md编辑格式，如果需其他版本可点击大佬链接查看
https://github.com/igarashikenshin/Hackintosh-Asus-Prime-Z390P_i9-9900K_RX6800XT
