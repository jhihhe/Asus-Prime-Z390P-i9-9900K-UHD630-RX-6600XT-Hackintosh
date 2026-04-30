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
  <a href="README_en.md">🇺🇸 English</a> | <a href="#简体中文">🇨🇳 简体中文</a>
</p>

---

## 📋 目录

- [项目介绍](#项目介绍)
- [硬件配置](#硬件配置)
- [EFI 结构](#efi-结构)
- [安装指南](#安装指南)
- [驱动更新日志](#驱动更新日志)
- [博通WiFi驱动指南](#博通wifi驱动指南)
- [常见问题](#常见问题)
- [许可证](#许可证)
- [贡献指南](#贡献指南)

---

## 🏠 项目介绍

本项目为 **ASUS PRIME Z390-P** 台式机提供完整的 OpenCore EFI 配置，支持安装和运行 macOS Sonoma、Ventura、Monterey、Catalina 以及最新的 **macOS 26 Tahoe**。

### ✨ 特性

- ✅ 支持 macOS 15.x (Sonoma) 到 macOS 26.x (Tahoe)
- ✅ 使用 OpenCore 1.0.8 MOD 核心
- ✅ 完整的硬件加速支持
- ✅ 博通 WiFi 无线网卡原生驱动
- ✅ 定制 AMD Radeon Pro W6600X 显卡配置
- ✅ 图形化 OpenCore 启动界面
- ✅ 支持 SIP 系统完整性保护管理

---

## 💻 硬件配置

| 组件 | 型号 | 状态 |
|------|------|------|
| 主板 | ASUS PRIME Z390-P | ✅ 已验证 |
| 处理器 | Intel Core i9-9900K | ✅ 已验证 |
| 核显 | Intel UHD Graphics 630 | ✅ 已验证 |
| 独显 | AMD Radeon RX 6600 XT | ✅ 已验证 |
| 有线网卡 | Realtek RTL8111H | ✅ 已验证 |
| 无线网卡 | Broadcom 黑苹果网卡 | ✅ 已验证 |
| 声卡 | Realtek ALC887 | ✅ 已验证 |
| 内存 | DDR4 | ✅ 已验证 |

---

## 🚀 安装指南

### 📌 前置要求

1. 一个 16GB 或更大的 USB 驱动器
2. Mac 机或黑苹果用于创建安装媒体
3. 下载 macOS 安装程序

### 🔧 安装步骤

#### 1️⃣ 准备 EFI 分区

```bash
# 格式化 USB 为 GPT 分区
# 创建 FAT32 分区，卷名为 EFI
```

#### 2️⃣ 复制 EFI 文件

将本项目的 `EFI` 文件夹完整复制到 USB 的 ESP 分区

#### 3️⃣ 配置 BIOS 设置

| 设置项 | 推荐值 |
|--------|--------|
| 快速启动 | 禁用 |
| 安全启动 | 禁用 |
| CSM 兼容 | 禁用 |
| XHCI Hand-off | 启用 |
| Above 4G Decoding | 启用 |
| Resizable BAR | 启用（如支持） |

#### 4️⃣ 启动安装

1. 插入 USB 并启动
2. 在 OpenCore 界面选择 `Install macOS`
3. 磁盘工具中格式化目标磁盘为 APFS
4. 选择 `安装 macOS` 开始安装

#### 5️⃣ 安装后配置

首次启动后建议运行 [OpenCore Configurator](https://mackie100projects.altervista.org/download-opencore-configurator/) 或 [ProperTree](https://github.com/corpnewt/ProperTree) 验证配置

---

## 📝 驱动更新日志

### v1.0.8 MOD (2025-04-30)

<p align="center">
  <img src="https://img.shields.io/badge/Date-2025--04--30-blue?style=flat-square" alt="Date">
  <img src="https://img.shields.io/badge/OpenCore-1.0.8%20MOD-green?style=flat-square" alt="OpenCore">
</p>

#### ✨ 核心更新

- OpenCore 升级至 1.0.8 MOD 版
- 全量更新内核扩展(kext)至最新稳定版本
- 新增 HFS+ 文件系统支持（hfsplus.efi）
- 定制 AMD Radeon Pro W6600X 显卡配置
- IOSkywalkFamily.kext 升级至 v1.2.0
- **新增 macOS 26.5 Tahoe 原生支持**
- 添加 BlueToolFixup.kext 蓝牙支持
- 优化 boot-args 兼容性参数

### v1.0.1 MOD (2024-09-05)

- OpenCore 更新至 1.0.1 MOD
- HFS+ 文件系统支持
- AMD Radeon Pro W6600 定制配置
- IOSkywalkFamily.kext v1.1.0

### v0.9.8a (2024-02-09)

- OpenCore 更新至 0.9.8 正式版
- IGPU 版本更新至 OC 1.01 MOD

---

## 📶 博通WiFi驱动指南

适用于 macOS Sonoma/Sequoia/Tahoe

### 🔧 使用 OpenCore Legacy Patcher

<p align="center">
  <a href="https://github.com/laobamac/OCLP-Mod/releases"><img src="https://img.shields.io/badge/Download-OCLP--Mod-red?style=for-the-badge" alt="Download OCLP-Mod"></a>
</p>

#### 📋 操作流程

1. **启动工具**
   - 运行 OpenCore Legacy Patcher 应用程序

2. **应用网络驱动补丁**
   - 双击 `Post-Install Root Patch` 功能模块
   - 在补丁列表中勾选：
     - ✅ `Networking: Modern Wireless`（推荐）
     - ✅ `Networking: Legacy Wireless`（旧设备备用）

3. **执行系统级修改**
   - 点击 `Start Root Patching` 初始化补丁进程
   - 在权限确认弹窗中选择 `Yes` 授权操作

4. **完成部署**
   - 等待进度条完成（约1-3分钟）
   - 点击 `Reboot` 重启系统生效

> 💡 **提示**：建议在系统更新后重新应用补丁以确保最佳兼容性

---

## ❓ 常见问题

### Q1: 博通 WiFi 无法使用？

**A**: 请确保已运行 OpenCore Legacy Patcher 的 Post-Install Root Patch

### Q2: 核显无法工作？

**A**: 当前配置中 `ig-platform-id` 为 `00003BE9`，如有问题请检查 `boot-args` 中的 `igfxfw=2`

### Q3: 安装时卡在何处？

**A**: 建议查看 [dortania/Hackintosh Vanilla Desktop Guide](https://github.com/dortania/OpenCore-Install-Guide) 获取详细排错信息

### Q4: 如何更新系统后保持 WiFi 工作？

**A**: 系统大版本更新后需要重新运行 OCLP 的 Root Patch

---

## 📜 许可证

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

## 🤝 贡献指南

欢迎提交 Issue 和 Pull Request！

### 提交问题

- 请描述具体的硬件配置和 macOS 版本
- 提供错误日志（如有）
- 说明问题的复现步骤

### 提交 PR

1. Fork 本仓库
2. 创建新分支 (`git checkout -b feature/amazing-feature`)
3. 提交更改 (`git commit -m 'Add amazing feature'`)
4. 推送到分支 (`git push origin feature/amazing-feature`)
5. 创建 Pull Request

---

## 🙏 致谢

- [OpenCore](https://github.com/acidanthera/OpenCorePkg) - 开源 EFI 引导程序
- [Acidanthera](https://github.com/acidanthera) - 所有驱动和补丁的开发者
- [Dortania](https://github.com/dortania) - Hackintosh 社区贡献者
- [OpenCore Legacy Patcher](https://github.com/dortania/OpenCore-Legacy-Patcher) - 旧硬件支持工具

---

<p align="center">
  <img src="https://img.shields.io/badge/Made%20with-❤️-red?style=for-the-badge" alt="Made with Love">
  <img src="https://img.shields.io/badge/Powered%20by-Hackintosh-blue?style=for-the-badge" alt="Powered by Hackintosh">
</p>

<p align="center">
  <strong>如果你觉得这个项目有帮助，请 ⭐ Star 支持！</strong>
</p>

---

## 🔗 相关链接

| 资源 | 链接 |
|------|------|
| GitHub 仓库 | https://github.com/jhihhe/Asus-Prime-Z390P-i9-9900K-UHD630-RX-6600XT-Hackintosh |
| OpenCore 官方文档 | https://dortania.github.io/OpenCore-Install-Guide/ |
| Dortania 社区 | https://github.com/dortania/OpenCore-Legacy-Patcher |
| AMD GPU 修复 | https://github.com/acidanthera/WhateverGreen |
| 声卡驱动 | https://github.com/acidanthera/AppleALC |

---

*最后更新: 2025-04-30 | OpenCore 1.0.8 MOD | 支持 macOS 26.5 Tahoe*
