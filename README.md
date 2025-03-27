# B460M OpenCore Hackintosh

这是一个基于OpenCore引导的Hackintosh项目，专门为B460M主板配置。

## 硬件配置

- 主板：B460M
- 处理器：Intel 10代处理器
- 显卡：Intel核显
- 声卡：Realtek ALC1220
- 网卡：板载网卡

## 系统要求

- macOS版本：支持macOS 11.0及以上版本
- OpenCore版本：0.8.0及以上

## 目录结构

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

## 主要功能

- 支持Intel核显驱动
- 支持Realtek ALC1220声卡
- 支持USB端口映射
- 支持电源管理
- 支持睡眠/唤醒功能

## 使用说明

1. 将EFI文件夹复制到ESP分区
2. 使用OpenCore Configurator打开config.plist
3. 根据您的具体硬件配置修改相关参数
4. 保存配置并重启

## 注意事项

- 首次安装时请确保BIOS设置正确
- 建议在安装前备份重要数据
- 如遇到问题，请检查config.plist中的配置是否正确

## 更新日志

### v1.0.0
- 初始版本发布
- 支持基本功能配置

## 贡献指南

欢迎提交Issue和Pull Request来帮助改进这个项目。

## 许可证

MIT License 