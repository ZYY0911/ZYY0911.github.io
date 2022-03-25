## 教程

有很多同学问我是怎么查看硬盘写入量的，这个是通过一个叫 smartctl 的应用实现的，使用 M1 Mac 安装 [smartctl](https://link.zhihu.com/?target=https%3A//www.smartmontools.org/) 的时候出现了一些问题，为了避免大家踩坑，我就整理了一下安装流程。

### 安装 HomeBrew

我是通过 Mac os 上的软件包管理工具 [HomeBrew](https://link.zhihu.com/?target=http%3A//brew.sh/) 来进行安装的，因此首先要做的就是安装上 HomeBrew，如果你的电脑上已经安装了 HomeBrew 则可以直接忽略这一步。

官网给出的方法十分简单，只需要在终端中粘贴如下代码即可：

```text
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

我也按照官网的提示进行安装，但因为一些众所周知的原因，这个方法失败了，终端中出现如下提示：

```text
raw.githubusercontent.com port 443: Connection refused
```

于是在我在网上查了一些资料，很多方法都是过了，踩了很多坑，我在这里就只放最后成功的方法吧，[原文连接](https://link.zhihu.com/?target=https%3A//blog.csdn.net/L_boyka/article/details/112554554%3Futm_medium%3Ddistribute.pc_relevant.none-task-blog-BlogCommendFromMachineLearnPai2-2.control%26dist_request_id%3D1f00f159-3fab-4ab0-a55f-8b97eb744e26%26depth_1-utm_source%3Ddistribute.pc_relevant.none-task-blog-BlogCommendFromMachineLearnPai2-2.control)

简单来说就是换源，在终端中输入以下代码即可：

```text
# 设置homebrew-core镜像
HOMEBREW_CORE_GIT_REMOTE=https://mirrors.ustc.edu.cn/homebrew-core.git

/bin/bash -c "$(curl -fsSL https://cdn.jsdelivr.net/gh/ineo6/homebrew-install/install.sh)"
```

等待安装完成后，需要设置环境变量，在终端中接着输入以下代码即可：

**注意：如果你确定使用的终端是zsh（一般默认是zsh），那么直接执行下面代码，否则请将两段的末尾的 zshrc 改为bashrc即可**

```text
echo export PATH=/opt/homebrew/bin:$PATH >> .zshrc
source ~/.zshrc
```

重启终端，并在其中输入 `brew` ，如果没有报错，则说明安装成功了。

关于安装 HomeBrew 的其他方法，可以参考这篇文章：

[晨 Sir：Mac必备神器Homebrew269 赞同 · 69 评论文章![img](https://pic1.zhimg.com/v2-8f1ea66d5742981916b04879ebd0325c_180x120.jpg)](https://zhuanlan.zhihu.com/p/59805070)

### 安装 smartctl

成功安装 HomeBrew 之后，我们就可以安装 smartctl 了！在终端中输入如下代码，即可进行安装：

```text
brew install smartmontools
```

在终端输入 `smartctl` ,如果没有报错则说明安装成功了。



![img](https://pic2.zhimg.com/80/v2-02a5650106944561996217a99ce1a3a5_1440w.png)smartctl



### 查看硬盘使用量

在终端中输入如下代码，即可进行看查硬盘使用量。

```text
smartctl -a disk0
```

结果如下，里面的Percentage Used 就是损耗值，Data Units Written 就是写入量。



![img](https://pic2.zhimg.com/80/v2-40f72d959d7f4686ede1a84189f88119_1440w.png)硬盘写入



## 写在结尾

由于 mac os 相对激进的 swap 策略，我这台 16G 的 MacBook Air 两个月时间写入了 1.4T 左右的数据，如果正常使用的话，这个数据放在 win 本中可能一年都写不到。不过这两个月中我确实没有因为内存不足而导致体验上的不佳，也只能说有利有弊吧。不过这一代 Mac 不支持更换 SSD，所以要想使用时间长一点还是建议 16G 起步比较好！



### 如何卸载

评论区有朋友问如何卸载这个工具，由于咱们使用的是brew包管理器安装的，那卸载也是十分的方便，只需要在终端输入下面的代码即可卸载成功：

```text
brew uninstall smartmontools 
```

- 3.22 日更新

![img](https://pic2.zhimg.com/80/v2-3c9257db5d6877bcae21d49fc563d1c1_1440w.jpg)