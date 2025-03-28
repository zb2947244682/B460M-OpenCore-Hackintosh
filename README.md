# 🍎 B460M OpenCore Hackintosh

这是一个基于 OpenCore 引导的 Hackintosh 项目，专门为 B460M 主板配置。本项目旨在帮助用户轻松实现 macOS 的安装和配置。

## 🖥️ 硬件配置

- 🏢 主板：技嘉 B460M AORUS PRO
- 💻 处理器：英特尔 Core i5-10400
- 💾 内存：64 GB ( 英睿达 DDR4 3200MHz 16GB x 2 / 金士顿 DDR4 3200MHz 16GB x 2 )
- 💽 硬盘：三星 SSD 970 EVO Plus 1TB
- 📡 网卡：博通 BCM94360Z4 无线网卡
- 🔊 声卡：瑞昱 ALC1220-VB 声卡（主板自带的声卡）
- 🎮 显卡：Intel核显 UHD 630

## ⚙️ 系统要求

- 🍎 macOS版本：支持 macOS Sonoma 14.3.2
- 🛠️ OpenCore版本：1.0.3

## 📁 目录结构

```
.
├── EFI
│   └── OC
│       ├── ACPI
│       ├── Drivers
│       ├── Kexts
│       ├── OpenCore.efi
│       └── config.plist
└── README.md
```

## ✨ 主要功能

- 🎮 Intel核显完美驱动
- 🔊 Realtek ALC1220声卡支持
- 🔌 USB端口完整映射
- ⚡ 完善的电源管理
- 💤 睡眠/唤醒功能支持
- 📡 无线网卡支持
- 🎯 性能优化

## 📝 使用说明

1. 将 EFI 文件夹复制到 ESP 分区
2. 使用 OpenCore Configurator 打开 config.plist
3. 根据您的具体硬件配置修改相关参数
4. 保存配置并重启

## ⚠️ 注意事项

- 首次安装时请确保 BIOS 设置正确
- 建议在安装前备份重要数据
- 如遇到问题，请检查 config.plist 中的配置是否正确
- 请确保使用最新版本的 OpenCore
- 建议在安装前阅读完整的文档

## 📅 更新日志

### v1.0.0
- 🎉 初始版本发布
- ✨ 支持 macOS Sonoma 14.3.2
- 🔧 基于 OpenCore 1.0.3
- 🎮 完善硬件驱动
- ⚡ 优化系统性能

## 🤝 贡献指南

欢迎提交 Issue 和 Pull Request 来帮助改进这个项目。您的贡献将使这个项目变得更好！

## 📄 许可证

MIT License

## 📞 联系方式

如有问题或建议，欢迎通过以下方式联系：
- 提交 Issue
- 发送邮件
- 加入讨论组

---
⭐ 如果这个项目对您有帮助，欢迎给个 Star 支持一下！ 