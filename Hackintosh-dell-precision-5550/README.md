# Hackintosh-dell-precision-5550
包含本机实践过的Catalina10.15.7系统和Sonoma14.6.1系统

cpu OctalCore Intel Core i7-10875H, 4600 MHz (46 x 100)
显卡  UHD630
声卡  Realtek ALC289
无线网卡  Intel(R) Wi-Fi 6 AX201 160MHz
触摸板键盘 PS/2 标准

两个版本应该都有些小问题，但是不影响使用，网络都是正常的

------

新上传的  Sonoma14.6.1-在用-流畅    顾名思义，很流畅



## 解锁cfg lock (仅在本机尝试)

工具（需要在config.plist中加入）

modGRUBShell（解锁）

VerifyMSR2 （查看是否解锁）

启动时选择modGRUBShell选项（OpenCore启动选择页面），在grub提示符下输入以下命令（第一行解锁CFG，第二行解锁超频）。

**注：开机界面如果不显示添加的工具，按空格！！！**

```
setup_var CpuSetup 0x3e 0x0     //解锁cfg lock
setup_var CpuSetup 0xda 0x0			//解锁超频
exit
```

重启笔记本电脑并启动至 BIOS。恢复出厂设置。现在您的 CFG 锁将被禁用。您可以通过运行 VerifyMSR2 选项来确认这一点。

如果更新 BIOS，则可能需要再次执行此操作

来源：[解锁cfg lock](https://github.com/lovvg/hackintosh_dell_precision_5550)

------

USB定制：

```
工具：USBToolBox-1.0.1-RELEASE

UTBMap.kext（USBToolBox生成）

USBToolBox.kext
```

注意取消 **XhciPortLimit** 勾选

来源：[**国光的黑苹果安装教程**](https://apple.sqlsec.com/6-%E5%AE%9E%E7%94%A8%E5%A7%BF%E5%8A%BF/6-1/)



最后。。。。。。。。。。

睡眠问题还是没解决，我放弃了，直接关闭睡眠.....................
