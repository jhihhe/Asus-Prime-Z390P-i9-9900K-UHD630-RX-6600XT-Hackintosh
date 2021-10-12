# Hackintosh-Asus_Prime_Z390P-i9-9900K_UHD630-EFI_OpenCore-0.7.5 macOS
下载点击[releases](https://github.com/jhihhe/Hackintosh-Asus_Prime_Z390P-i9-9900K_UHD630-EFI_OpenCore-0.7.3-macOS/releases)

![系统信息](https://i.loli.net/2021/10/07/9SxCGFkKJvq7QjR.png)![系统信息](https://i.loli.net/2021/08/12/cyBZNPtbaU41hAE.png)

### 配置
1. 主板: ASUS PRIME Z390-P
1. CPU: Intel® Core™ i9-9900K Processor
1. 核显: Intel® UHD Graphics 630
1. 板载网卡: Realtek® RTL8111H Gigabit LAN Controller
1. WiFi/蓝牙: BCM943602CS（BT4.2）
1. 声卡: Realtek® ALC 887 8-Channel High Definition Audio
1. 固态硬盘: 西数SN750 500GB
![硬盘信息](https://i.loli.net/2021/10/02/UlzBGydZqkTjRQc.png)
### BIOS设置
1. 高级-CPU设置--Intel(VMX) Virtualization Technology -enable
1. 高级-北桥-显示设置--首选显卡-Auto，初始化IGPU-enable，DVMT Pre-Allocated-1024M，RC6-auto
1. 高级-USB Configuration--XHCI Hand-off -enable
1. 高级-内置设备-Serial Port Configuration-Serial Port -off
1. 启动-启动设置--快速启动-disable，若出现错误等待按下F1键-disable
1. 设置模式-高级模式

# **可适用操作系统版本：macOS Catalina 10.15.1～Big Sur 11.6/支持macOS Monterey 12.0 **

1. OpenCore版本：0.7.5（内含主题如下图） ![主题](https://i.loli.net/2021/09/11/t4FBZPeHkwdufiG.png)![主题](https://i.loli.net/2021/07/31/uFHJD2BMazqmTcA.png)
1. CPU变频：正常。
1. UHD630：正常，VRAM动态，最大值：4095 MB，开启HIDPI，开启H.264&HEVC硬件解码加速 ![显卡](https://i.loli.net/2021/07/23/nSDZyHCFM9KbvwO.png) ![硬件解码加速：H.264&HEVC解码](https://i.loli.net/2021/07/23/cu7ZCYEIqe3sROt.png)
1. 3.5mm声音
1. USB：正常，Big Sur 11.3版本后，如USB加载不正常，需自行定制usb，或取消加载USBport.kext，将XhciPortLimit值变更为true。(备用USBInjectAll驱动在根目录) ![USB](https://i.loli.net/2021/06/12/1XyQrsM7m2paN4f.png)
1. 有线网卡：正常，使用了RealtekRTL8111.kext。 ![有线网卡](https://i.loli.net/2021/06/12/29lJdKBqonkjtcp.png)
1. 无线网卡：正常 ![Wi-Fi](https://i.loli.net/2021/06/12/ilADj9OuVmFsztp.png)
1. 睡眠唤醒：正常。![睡眠](https://i.loli.net/2021/06/12/1K98Dbj3eFywfnY.png)
1. 关机开机：正常。
1. iCloud & App Store & iMessage & FaceTime：请自行生成Board Serial Number、序列号、SmUUID，并相应的修改SysPrameter系统参数中的“自定义UUID”，和RtVariables变量设置中的MLB、ROM。
1. AirDrop & HandOff & Continuity：正常。
![Wi-Fi](https://i.loli.net/2021/06/12/1UrwpiNsKfIb8g3.png)
![蓝牙](https://i.loli.net/2021/06/12/DJma7dLzorEniOp.png)

### Tips：

1. 机型需设定为iMAC19.1（现已预置，安装完成后请自行修改）。
1. 该config默认为无verbose模式。如需启用verbose模式，config.plist需要修改以下一项：NVRAM-Add-7C436110-AB2A-4BBB-A880-FE41995C9F82-boot-args，添加-v。
1. 该config启动盘策略 ScanPolicy 值设置为0。可引导Windows或Other OS（Linux、Unix）如需指定搜索分区类型，可参考OC配置手册。

# 鸣谢 
# 采用了igarashikenshin的README.md编辑格式，如果用A卡独显或需其他版本可点击大佬链接查看
https://github.com/igarashikenshin/Hackintosh-Asus-Prime-Z390P_i9-9900K_RX6800XT
