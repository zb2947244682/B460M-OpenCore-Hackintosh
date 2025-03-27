# 技嘉 B460M AORUS PRO 黑苹果 EFI

这是一个为技嘉 B460M AORUS PRO 主板，搭配英特尔 i5-10400 处理器设计的 OpenCore 1.0.4 EFI 配置。

## 系统配置

- 主板: 技嘉 B460M AORUS PRO
- 处理器: 英特尔 Core i5-10400
- 内存: 64GB DDR4 (英睿达 + 金士顿)
- 显卡: 英特尔 UHD Graphics 630
- 硬盘: 三星 SSD 970 EVO Plus 1TB
- 声卡: 瑞昱 @ 英特尔 High Definition Audio 控制器
- 有线网卡: 英特尔 Ethernet Connection I219-V
- 无线网卡: Broadcom 802.11ac Network Adapter BCM94360Z4

## 使用说明

1. 将此EFI文件夹复制到您的引导分区中
2. 根据 `missing_files.txt` 中的说明，下载或生成所需的缺失文件
3. 使用 OpenCore 配置器或文本编辑器调整 `config.plist` 中的序列号和其他细节
4. 重启电脑进入 BIOS 设置:
   - 禁用 CFG Lock
   - 禁用 VT-d
   - 禁用 CSM
   - 启用 XHCI Hand-off
   - 将 DVMT Pre-Allocated 设置为 64MB

## 工作状态

当完成所有缺失文件的补充后，您可以期待以下功能正常工作:

- [x] 英特尔 UHD 630 图形加速
- [x] 音频输出
- [x] 有线网络
- [x] 无线网络和蓝牙 (BCM94360Z4 免驱)
- [x] USB 端口
- [x] 睡眠/唤醒
- [x] iMessage 和 FaceTime (需正确设置三码)

## 注意事项

- 首次启动时，建议添加启动参数 `-v` 以查看详细的启动信息
- 如遇到引导问题，尝试添加 `keepsyms=1 debug=0x100` 参数
- 安装完成后，建议重新生成一套新的三码 (MLB、ROM、序列号)

## 参考资料

- [OpenCore 安装指南](https://dortania.github.io/OpenCore-Install-Guide/)
- [OpenCore 参考手册](https://dortania.github.io/docs/latest/Configuration.html)
- [Comet Lake 配置指南](https://dortania.github.io/OpenCore-Install-Guide/config.plist/comet-lake.html) 