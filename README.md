# 300-series-hackintosh-mojave

作者：**Genius-lbesT** QQ2489050703

加入QQ群：724096369 **黑苹果Genius**

# 本教程制作为8/9代台式机CPU通用的安装及完善驱动.

AMD / NVDIA / INTEL均可通过EFI-for-install.zip安装到机器上.

EFI蓝本为黑果小兵daliansky博客 blog.daliansky.net 的镜像with clover 4928（nvdia)/clover 4928(AMD+INTEL)提取.

NVDIA支持10.13.6/AMD+INTEL支持最新版本mojave10.14.5

感谢黑果小兵daliansky



# 正文

##### AMD / NVDIA / INTEL均可通过EFI-for-install.zip安装到机器上.

EFI蓝本为黑果小兵daliansky博客 blog.daliansky.net 的镜像with clover 4903（nvdia)/clover 4928(AMD+INTEL)提取.

NVDIA支持10.13.6/AMD+INTEL支持最新版本mojave10.14.5

感谢黑果小兵daliansky

#### AMD+INTEL-Mojave 10.14.5

镜像下载：https://blog.daliansky.net/macOS-Mojave-10.14.5-18F132-official-version-with-Clover-4928-original-image.html

#### AMD+INTEL-Mojave 10.14.4

镜像下载： https://blog.daliansky.net/macOS-Mojave-10.14.4-18E226-official-version-with-Clover-4903-original-image.html

#### Nvdia-High Sierra 10.13.6

镜像下载：https://blog.daliansky.net/macOS-High-Sierra-10.13.6-17G65-Release-Version-with-Clover-4596-original-mirror.html



### 一、安装教程

https://github.com/Lubibest/How-to-install-a-Hackintosh

### 二、安装

#### 1.AMD-rx显卡

AMD免驱显卡推荐安装mojave10.14.5，镜像下载地址：

https://blog.daliansky.net/macOS-Mojave-10.14.5-18F132-official-version-with-Clover-4928-original-image.html

安装教程：https://github.com/Lubibest/How-to-install-a-Hackintosh

用**clover configurator**替换U盘的**ESP分区**的EFI文件为**EFI-for-after install-AMD-rx.zip**

重启生效

AMD显卡的机器将持续得到clover升级的支持

#### 2.AMD-vega显卡

AMD免驱显卡推荐安装mojave10.14.5，镜像下载地址：

https://blog.daliansky.net/macOS-Mojave-10.14.5-18F132-official-version-with-Clover-4928-original-image.html

安装教程：https://github.com/Lubibest/How-to-install-a-Hackintosh

用**clover configurator**替换U盘的**ESP分区**的EFI文件为**EFI-for-after install-AMD-vega.zip**

重启生效

AMD-vega显卡的机器将持续得到clover升级的支持

### 3.intel

Intel UHD630 核显推荐安装mojave10.14.5

镜像下载地址：

https://blog.daliansky.net/macOS-Mojave-10.14.5-18F132-official-version-with-Clover-4928-original-image.html

安装教程：https://github.com/Lubibest/How-to-install-a-Hackintosh

用clover configurator替换U盘的ESP分区的EFI文件为EFI-for-after install-intel.zip  

PS：intel注入为0X12345678,请查阅核显ID列表查找并尝试驱动或通过Hackintool注入补丁，本教程为对核显机器完善驱动。

intel的机器将会持续得到clover升级的支持

#### 4.NVDIA显卡的机器

nvdia显卡推荐安装10.13.6（17G65)，镜像下载地址：

https://blog.daliansky.net/macOS-High-Sierra-10.13.6-17G65-Release-Version-with-Clover-4596-original-mirror.html

安装教程：https://github.com/Lubibest/How-to-install-a-Hackintosh

请在安装完成后使用终端运行下面的命令，并用clover configurator替换U盘的ESP分区的EFI文件为EFI-for-after install-nvdia.zip

bash <(curl -s https://raw.githubusercontent.com/Benjamin-Dobell/nvidia-update/master/nvidia-update.sh)

重启生效

由于nvdia显卡无法更新os版本，我将不再为nvdia显卡的机器更新clover。

### 三、本教程中已放入applealc.kext，并未添加声卡ID

请根据自己的声卡型号尝试注入声卡ID，声卡ID请查阅下面这篇教程：

#### AppleALC支持的Codecs列表及AppleALC的使用

https://blog.daliansky.net/AppleALC-Supported-codecs.html

常用ALC：

alc 887 注入 5/7

alc 892 注入 1/2

a1220 注入 1/2

s1220a 注入 1/2

注入位置：

**「clover configuratoer」**

Devices/Audio/inject(手动输入）

![](https://github.com/Lubibest/300-series-hackintosh-mojave/blob/master/appleALC.png)

### 四、注意事项

安装过程如果遇到任何问题，请查阅黑果小兵的两篇教程,如下：

#### macOS Mojave 10.14安装中常见的问题及解决方法:

https://blog.daliansky.net/Common-problems-and-solutions-in-macOS-Mojave-10.14-installation.html

#### macOS 10.13安装中常见的问题及解决方法

https://blog.daliansky.net/macOS-10.13-installation-of-common-problems-and-solutions.html

### 五、本教程适用的主板包括

#### ·微星H310,微星B360,微星Z370，微星Z390

##### 关于微星主板的测试结果：

经测试，微星系列B360/Z390系列的最新的BIOS通过本文方法无法安装

##### 解决方案：

##### 1.通过降级到官方发布的2018年5月至8月之间的BIOS，可以正常安装，并没有任何问题（可以用过正常的手段刷入，刷BIOS要求，U盘格式FAT32,USB2.0刷入）

##### 2.通过添加RTC补丁，可以进行安装，关于RTC补丁的说明：https://github.com/acidanthera/RTCMemoryFixup

##### 3.Z390系列无法安装的请添加RTC补丁并尝试

#### ·技嘉H310,技嘉B360,技嘉Z370，技嘉Z390

关于技嘉主板的测试结果：

##### 如通过本文方法无法安装的，请尝试替换SMC驱动，或添加RTC补丁

#### ·华硕H310,华硕B360,华硕Z370,华硕Z390

关于华硕主板的测试结果：

经测试，华硕B360和Z390系列新版本的BIOS通过本文方法可能无法安装

#### 解决方法：

##### 1.通过降级BIOS（目前还未明确能正常安装的BIOS版本）(无法通过正常手段刷入，需要BIOS夹子）

##### 2.在kext/other中的替换一个文件，即可：

-----删除FakeSMC.KEXT,放入VirtualSMC.kext

#### ·昂达H310C

或

#### ·H310,B360,Z370，Z390芯片组的台式机电脑

具体请自行测试。

欢迎大家把测试结果反馈给我

如有疑问，请添加QQ：2489050703 Genius-lbesT

### 六、AMD显卡的EFI将在后续的os版本升级中得到更新

### 七、其他

#### 适用于HD530的100系主板的请阅读：

https://github.com/Lubibest/100-series-hackintosh-mojave

#### 适用于hd630的200系主板的请阅读：

https://github.com/Lubibest/200-series-hackintosh-mojave

### 八、本教程EFI

由

-垃圾帮主-修改制作

-Genius lbesT-发布

作者：Genius-lbesT QQ2489050703

加入QQ群：724096369 黑苹果Genius
