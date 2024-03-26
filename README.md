[中文](README.md)
[English](README_EN.md)
# LXC-DOCKER-KernelSU_Action

## 支持的内核版本
4.9&emsp;&emsp;4.14&emsp;&emsp;4.19&emsp;&emsp;5.4

## 说明 
> 有的工作流是用谷歌的 clang 12.0.5编译器

> 有的工作流是用谷歌的 clang 14 编译器

> 有的工作流是用从clang官方源码编译的 clang 18 编译器

> 其中zyc clang 18 和 阿菌•未霜 clang 18可以任选，阿菌•未霜 clang 18 带BOLT等优化

<br>

## 步骤
1. fork本仓库到你的仓库，先打开config.env，编辑变量，Commit changes
2. 上方菜单选择Actions，选择All workflows，不同工作流的区别看名字就知道了，选择自己想运行的工作流
3. 然后点击 run workflow,再确认一次，就启动了，等待完成
4. 从下方Artifacts 下载编译好的内核

<br>

## 提示
- 如果编译不过，请采用clang 14 或者 clang 12 编译
- 上方菜单选择Actions，选择All workflows，可以看到所有工作流
- config.env文件里有对应的变量说明
- 高端机在这里尤其指的是AB分区机子，比如一加8T、红米K30pro、小米10等，没备注的工作流都是低端机，比如小米6、红米5plus、红米note4x、红米4、红米4a等

<br>

## 一些修复方法
### 关于k30pro内核源码和一加9R的los内核源码，编译完成后，不生成Image.gz和Image.gz-dtb文件
### 解决办法
在内核配置文件最后加入以下3行配置，再进行编译
```
CONFIG_BUILD_ARM64_KERNEL_COMPRESSION_GZIP=y
CONFIG_BUILD_ARM64_APPENDED_DTB_IMAGE=y
CONFIG_BUILD_ARM64_DT_OVERLAY=y
```
### .py文件报print语法错误
### 解决方法
env.sh里切换python2，即SWITCH_PYTHON=后面填写true

<br>

## 感谢
- [AnyKernel3](https://github.com/osm0sis/AnyKernel3)
- [AOSP](https://android.googlesource.com)
- [KernelSU](https://github.com/tiann/KernelSU)
- [xiaoxindada](https://github.com/xiaoxindada)
- [xiaoleGun](https://github.com/xiaoleGun/KernelSU_Action)
- [wu17481748](https://github.com/wu17481748/LXC-DOCKER-KernelSU_Action)
- [qiuqiu](https://github.com/lateautumn233)
- [zyc clang](https://github.com/ZyCromerZ/Clang)
- [Mandi-Sa](https://github.com/Mandi-Sa/clang)
