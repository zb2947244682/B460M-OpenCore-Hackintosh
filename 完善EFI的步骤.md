# 完善 EFI 的步骤

## 目前状态

你的EFI配置已基本完成，包括：

1. ACPI文件已经放置到位，并在config.plist中引用了正确的文件名
2. config.plist已经正确配置，适用于B460M AORUS PRO主板和i5-10400处理器
3. 所有必要的Kext驱动文件已经复制到EFI/OC/Kexts/目录
4. 已创建基本的USBPorts.kext结构
5. 已复制OcBinaryData的图形界面资源文件并启用相关配置
6. 已启用开机音效支持

## 仍需完成的步骤

### 1. 生成SMBIOS信息

在安装前，使用GenSMBIOS工具为你的系统生成唯一的序列号信息，并更新到config.plist文件中：

1. 下载并运行[GenSMBIOS](https://github.com/corpnewt/GenSMBIOS)
2. 选择选项3: Generate SMBIOS
3. 输入型号: iMac20,1
4. 将生成的信息复制到config.plist中的PlatformInfo > Generic部分

### 2. BIOS设置

在启动安装前，确保BIOS做出以下设置：

- 禁用: CFG Lock, VT-d, CSM, Fast Boot
- 启用: VT-x, Above 4G decoding, Hyper-Threading
- DVMT Pre-Allocated: 64MB
- XHCI Hand-off: 启用
- 安全启动: 禁用

### 3. 安装后的配置

安装完成macOS后，你需要进行以下配置：

1. 使用Hackintool创建自定义USBPorts.kext，替换当前的基础USBPorts.kext
2. 如果声卡不工作，尝试在boot-args中修改alcid值（1-99）
3. 如果遇到睡眠问题，参考README.md中的故障排除部分

## 验证安装

安装完成后，所有硬件功能应该正常工作：

- 图形加速（Intel UHD 630）
- 音频输出
- 有线和无线网络
- USB端口
- 睡眠/唤醒
- iServices（需要正确设置SMBIOS信息）

祝你安装顺利！ 