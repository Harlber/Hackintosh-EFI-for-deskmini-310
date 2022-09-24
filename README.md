# Hackintosh-EFI-for-deskmini-310


EFI 配置 OpenCore 0.7.5

### 配置
- 主机: deskmini 310
- cpu: intel i5 8400/9400/10400
- 十铨 火神 DDR4 2666 8G*2 等笔记本内存（16+8也ok）
- 三星 970 EVO  
- ID-COOLING IS-40X 散热器
- DW1820A 无线网卡+2天线（蓝牙wifi免驱可购买博通系列或拆机卡，其他移步 https://github.com/OpenIntelWireless/itlwm）
- 显示器 dell 1920*1080

### 安装前设置

1.镜像下载制作
 - softwareupdate --list-full-installers （无需登录appleid 获取镜像）
 - softwareupdate --fetch-full-installer --full-installer-version 12.5.1 （下载指定版本安装程序）
 - sudo /Applications/Install\ macOS\ Monterey.app/Contents/Resources/createinstallmedia --volume /Volumes/你的U盘名称
 
2.复制对应版本的efi至启动盘EFI中
 - diskutil list
 - sudo diskutil mount disk0s1
 
Bios Set:

1. Load UEFI Defaults

2. Advanced

   - Onboard HD Audio: Enabled
   - USB Configuration, XHCI Hand-off, Enabled （关键）
   - Super IO Configuration, Serial Port, Disabled（必须）

3. Security Secure Boot, Disabled(by default)

4. CSM disable


EFI Set:

​	把启动U盘中的EFI删除，使用新的EFI进行替换(记得修改为自己序列号)

### 参考

  - https://blog.xjn819.com/post/opencore-guide.html
  - https://support.apple.com/zh-cn/guide/deployment/depc4c80847a/web
  - https://www.iplaysoft.com/macos-usb-install-drive.html
  - https://github.com/OpenIntelWireless/itlwm
