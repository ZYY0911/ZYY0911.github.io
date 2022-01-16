---
layout: post
title: Android配置ADB
subtitle: Windows
categories: markdown
author: 老八
categories: zyy
tags: Windows AndroidADB
---

在Android studio中的设置产看本机SDK安装目录
<img src="https://img-blog.csdnimg.cn/20200329182107687.png"   width="60%">

复制目录跳转到文件夹

<img src="https://img-blog.csdnimg.cn/20200329182215639.png"   width="60%">

选择进入到

<img src="https://img-blog.csdnimg.cn/20200329182326807.png"   width="80%">

复制红框中的目录C:\Users\win10\AppData\Local\Android\Sdk\platform-tools
右键此电脑属性


<img src="https://img-blog.csdnimg.cn/20200329182840956.jpg"   width="80%">


<img src="https://img-blog.csdnimg.cn/20200329182902665.png"   width="60%">

新建系统环境变量 注意 变量值为刚才复制的路径
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200329182950548.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MzgyNjEwOQ==,size_16,color_FFFFFF,t_70#pic_center)
在找到Path点击编辑
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200329183220281.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MzgyNjEwOQ==,size_16,color_FFFFFF,t_70#pic_center)
点击新建 输入刚才%Android_Sdk%      (为刚才新建的的变量名)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200329183238329.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MzgyNjEwOQ==,size_16,color_FFFFFF,t_70#pic_center)
最后在cmd中输入adb shell   注意需要先把手机连到电脑或者模拟器打开
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200329183518287.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MzgyNjEwOQ==,size_16,color_FFFFFF,t_70#pic_center)
配置成功
