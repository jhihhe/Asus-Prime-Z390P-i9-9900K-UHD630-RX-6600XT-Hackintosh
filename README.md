# 🍎 Asus Prime Z390-P Hackintosh 黑苹果配置指南

![Hackintosh Screenshot](https://i.postimg.cc/yYVcNt5H/i-Shot-2022-07-01-09-57-21.png)
![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20macOS%20%7C%20Linux-green)

[中文](https://github.com/jhihhe/Asus-Prime-Z390P-i9-9900K-UHD630-RX-6600XT-Hackintosh/blob/main/README.md) | [English](https://github.com/jhihhe/Asus-Prime-Z390P-i9-9900K-UHD630-RX-6600XT-Hackintosh/blob/main/README-EN.md)

## 📥 下载指南
[![Release](https://img.shields.io/badge/Download-Releases-blue?style=for-the-badge&logo=github)](https://github.com/jhihhe/Asus-Prime-Z390P-i9-9900K-UHD630-RX-6600XT-Hackintosh/releases)  

> 💡 注意：  
> - 仅使用核显请下载 **IGPU 版本**  
> - 需自行生成：  
>   `Board Serial Number` | `序列号` | `SmUUID`  
>   ➤ 修改 `SysParameter` 中的 "自定义UUID"  
>   ➤ 修改 `RtVariables` 中的 `MLB` 和 `ROM`

---

## 🚀 更新日志
  - ✅ OpenCore 升级至 1.0.5 MOD 版
  - ✅ 所有 Kext 驱动更新至最新版本
  - ✅ 新增 hfsplus.efi 支持 U 盘安装

---

## ⚙️ 硬件配置
| 组件         | 型号                                      |
|--------------|------------------------------------------|
| 主板         | ASUS PRIME Z390-P (BIOS 3006) [下载](https://www.asus.com/us/motherboards-components/motherboards/prime/prime-z390-p/HelpDesk_BIOS/)   |
| CPU          | Intel Core i9-9900K                      |
| 散热         | THERMALRIGHT Frost Commander 140 BLACK   |
| 核显         | Intel UHD 630 (IGPU 专用版本可用)         |
| 独显         | AMD Radeon RX 6600 XT                    |
| 网卡         | Realtek RTL8111H 千兆网卡                |
| 无线/蓝牙    | BCM943602CS (BT4.2)                      |
| 声卡         | Realtek ALC 887                          |
| 存储         | WD SN750 500GB (TRIM 已开启)             |

![硬盘信息](https://tva1.sinaimg.cn/large/cec1774cly8h057sy9inrj21860u0tcy.jpg)

---

## ⚡ BIOS 设置
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

## 🍏 系统兼容性
**支持版本**: macOS Catalina ~ macOS Sequoia   
**OpenCore**: 1.0.5

![主题界面](https://tva2.sinaimg.cn/large/cec1774cly8h1g75kzm0vj21hc0u0gmt.jpg)  

---

## ✅ 功能验证
| 功能               | 状态 | 备注 |
|--------------------|------|------|
| CPU 变频           | ✔️   | [查看截图](https://tva4.sinaimg.cn/large/cec1774cly8h057spanbgj21860u0dio.jpg) |
| 核显/独显加速      | ✔️   | HIDPI/H.264/HEVC 支持 |
| 音频输出           | ✔️   | 3.5mm 接口正常 |
| USB 3.0            | ✔️   | 需定制 USBPorts.kext |
| 有线网络           | ✔️   | RealtekRTL8111.kext |
| 无线网络 & 蓝牙    | ✔️   | BCM943602CS 驱动正常 |
| 睡眠/唤醒          | ✔️   | S3 睡眠支持 |
| Apple 服务         | ✔️   | iCloud/iMessage 等全功能正常 |

---

## 📝 使用提示
1. **机型设置**: 默认使用 `iMac19,1`（安装后需自行修改）
2. **Verbose 模式**: 在 `boot-args` 添加 `-v`
3. **多系统引导**: ScanPolicy=0 支持 Windows/Linux
4. **USB 问题**: 
   - macOS 11.3+ 需禁用 USBPorts.kext
   - 设置 `XhciPortLimit=true`

---

## 🙏 致谢
本项目参考了 [igarashikenshin](https://github.com/igarashikenshin/Hackintosh-Asus-Prime-Z390P_i9-9900K_RX6800XT) 的配置方案，特别感谢黑苹果社区的各位开发者！
