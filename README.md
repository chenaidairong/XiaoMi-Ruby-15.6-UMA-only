＃XiaoMi-Ruby-15.6-UMA-only

＃＃ 警告

此配置仅适用于没有Nvidia Graphics的i5-8250U。您可能需要使用i3或i7版本更改配置。而且，如果您具有nvidia图形，则可能需要将其阻止。如果使用dw-serials无线网卡，则可能需要自己添加kext。

触控板在我的计算机上为CUST0001，如果无法驱动，请在Windows中查找设备名称并设置问题！

##从三叶草到Opencore

1.使用脚本解锁CFG并设置DVMT

2.在OpenCore引导页面中按Space，然后选择Clean NVRAM entry

＃＃ 特征

1. Opencore Bootloader和所有Hotpatch ACPI表

2.解锁CFG和DVMT限制，mac更原始

3.即使FN-Backlight按钮，99％的硬件也是完美的

＃＃ 硬件

对于仅适用于Xiaomi-Ruby-15.6-UMA的99％完美的Hackintosh，您需要执行以下操作。

1.将无线网络卡从Realtek更换为BCM94360CS2-必要

2.将显示器从45％NTSC更换为72％NTSC（N156HCE-ZH1）-可选

3.将m2 ssd从SATA替换为NVME-可选

4.升级内存-可选

5.购买优质的蓝牙条形音箱-可选

## BIOS设置

1.设置BIOS密码并禁用安全启动-必要

2.使用脚本解锁CFG并设置DVMT-推荐（您可以通过还原BIOS设置来回滚）

    您可以在Opencore引导页面中进行测试

##工作不顺利

1.内部扬声器（英特尔®智能声音技术）

    使用英特尔SST的笔记本电脑将无法通过它们（通常是内置麦克风）进行任何连接，因为它不受支持。您可以在Windows上使用设备管理器进行检查。
  
2. Realtek SD卡读卡器
 
    您可以将其传递到VirtualMachine，因为它是USB设备！
    
##内部扬声器解决方案

硬件破解可能会导致保证损失！

在Ruby中添加一个蓝牙声音模块，并让内部扬声器从中获得声音。

！[image]（https://github.com/XenOriginal/XiaoMi-Ruby-15.6-UMA-only/blob/master/Bild/BlueToothSoundModule_1.jpg）

！[image]（https://github.com/XenOriginal/XiaoMi-Ruby-15.6-UMA-only/blob/master/Bild/BlueToothSoundModule_2.jpg）

1，M38蓝牙声音模块

2，SH1.0 4p连接器

3，USB接口

##生成自己的SMbios

  平台信息

  为了设置SMBIOS信息，我们将使用CorpNewt的GenSMBIOS和ProperTree应用程序。 https://github.com/corpnewt/GenSMBIOS https://github.com/corpnewt/ProperTree

  由于存在KabyLake R，我们将选择MacBookPro14,2 SMBIOS：

  运行GenSMBIOS，选择选项1（用于下载MacSerial）和选项3（用于选择SMBIOS）。这将为我们提供类似于以下内容的输出：

  类型：MacBookPro14,2

  序列号：C02WXAY2HV2N

  电路板编号：C02826303CDHRPC8C

  SmUUID：88AA1336-8DF9-477A-A39F-03D016ED0809

  订单是产品|序列号|板级串行（MLB）

  类型部分将复制到通用-> SystemProductName。

  串行部分将复制到通用-> SystemSerialNumber。

  电路板序列号部分将复制到通用-> MLB。

  SmUUID部分将复制到Generic-> SystemUUID。

  我们将Generic-> ROM设置为Apple ROM（从真实Mac转储），您的NIC MAC地址或任何随机MAC地址（可以是6个随机字节），对于本指南，我们将使用11223300 0000。关于如何查找真实MAC地址的Fixing iServices页面）

  提醒您，您想要一个无效的序列号或有效的序列号，但未使用的序列号，您想获得一条消息，例如：“无效的序列号”或“未验证购买日期”

  Apple Check Coverage页面https://checkcoverage.apple.com/cn/zh/
  
## OpenCore当前状态

  主题有限

  在OpenCore引导页面中按Space，然后选择Clean NVRAM entry

  需要更多测试...

##捐赠

  ！[image]（https://github.com/XenOriginal/XiaoMi-Ruby-15.6-UMA-only/blob/master/Bild/AlipayCollectCode.jpg）
  ！[image]（https://github.com/XenOriginal/XiaoMi-Ruby-15.6-UMA-only/blob/master/Bild/WechatCollectCode.png）
