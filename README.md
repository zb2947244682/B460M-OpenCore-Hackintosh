# B460M AORUS PRO OpenCore 黑苹果 EFI

此EFI配置适用于技嘉 B460M AORUS PRO 主板搭配英特尔酷睿 i5-10400 处理器的黑苹果系统。

## 硬件配置

- 主板: 技嘉 B460M AORUS PRO
- CPU: 英特尔 Core i5-10400 @ 2.90GHz 六核
- 内存: 64 GB (英睿达 DDR4 3200MHz 16GB x 2 / 金士顿 DDR4 3200MHz 16GB x 2)
- 显卡: 英特尔 UHD Graphics 630
- 硬盘: 三星 SSD 970 EVO Plus 1TB
- 无线网卡: Broadcom 802.11ac Network Adapter BCM94360Z4

## 完成EFI配置步骤

### 1. 下载所需的ACPI文件

将以下ACPI文件下载并放置到 `EFI/OC/ACPI/` 目录下：

- [SSDT-PLUG.aml](https://github.com/dortania/Getting-Started-With-ACPI/raw/master/extra-files/compiled/SSDT-PLUG-DRTNIA.aml) - 处理器电源管理
- [SSDT-EC.aml](https://github.com/dortania/Getting-Started-With-ACPI/raw/master/extra-files/compiled/SSDT-EC-DESKTOP.aml) - 仿冒嵌入式控制器
- [SSDT-AWAC.aml](https://github.com/dortania/Getting-Started-With-ACPI/raw/master/extra-files/compiled/SSDT-AWAC.aml) - RTC 修复

### 2. 下载所需的Kext驱动

将以下驱动下载并放置到 `EFI/OC/Kexts/` 目录下：

- [Lilu.kext](https://github.com/acidanthera/Lilu/releases) - 必要的内核补丁平台
- [VirtualSMC.kext](https://github.com/acidanthera/VirtualSMC/releases) - 仿冒SMC
  - 同时还需要下载以下传感器插件:
    - SMCProcessor.kext
    - SMCSuperIO.kext
- [WhateverGreen.kext](https://github.com/acidanthera/WhateverGreen/releases) - 显卡补丁
- [AppleALC.kext](https://github.com/acidanthera/AppleALC/releases) - 声卡驱动
- [IntelMausi.kext](https://github.com/acidanthera/IntelMausi/releases) - 英特尔有线网卡驱动
- [AirportBrcmFixup.kext](https://github.com/acidanthera/AirportBrcmFixup/releases) - 博通无线网卡驱动

### 3. 创建USB映射驱动

使用Hackintool工具创建一个定制的USBPorts.kext，并放置到 `EFI/OC/Kexts/` 目录下。

### 4. 生成唯一的SMBIOS信息

使用[GenSMBIOS](https://github.com/corpnewt/GenSMBIOS)工具为你的配置生成唯一的SMBIOS信息：

1. 下载并运行GenSMBIOS
2. 选择"Generate SMBIOS"选项
3. 输入型号"iMac20,1"
4. 生成的信息复制到config.plist文件的PlatformInfo > Generic部分

### 5. 资源文件（可选）

如果需要图形化的启动界面，下载[OcBinaryData资源文件](https://github.com/acidanthera/OcBinaryData)，并将Resources文件夹复制到 `EFI/OC/` 目录下。

## 特别说明

1. 本配置已针对技嘉B460M AORUS PRO主板和i5-10400处理器优化
2. 声卡使用alcid=1参数，如果音频不工作，可以尝试其他布局ID
3. 确保在BIOS中禁用CFG-Lock，以获得更好的性能
4. 如果遇到启动问题，可以尝试在boot-args中添加-v参数进入啰嗦模式排查

## 问题解决

如果你遇到以下问题，可以尝试这些解决方案：

- **找不到引导项**：确保在BIOS中禁用安全启动，并将UEFI设为首选启动模式
- **显示器黑屏**：尝试在config.plist中添加igfxonln=1到boot-args
- **睡眠唤醒问题**：添加swd_panic=1到boot-args

## 版本历史

- 2025.03.27: 初始版本，基于OpenCore 0.7.9 