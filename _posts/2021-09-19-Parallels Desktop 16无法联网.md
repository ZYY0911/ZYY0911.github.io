---
layout: post
title: Parallels Desktop 16无法联网
subheading: 
    Mac虚拟机
author: 老八
categories: 老八
banner:
  video: https://vjs.zencdn.net/v/oceans.mp4
  loop: true
  volume: 0.8
  start_at: 8.5
  image: https://bit.ly/3xTmdUP
  opacity: 0.618
  background: "#000"
  height: "100vh"
  min_height: "38vh"
  heading_style: "font-size: 4.25em; font-weight: bold; text-decoration: underline"
  subheading_style: "color: gold"
tags: Mac ParallelsDesktop 网络
sidebar: []
---

## 注意
当前版本Parallels Desktop Business Edition 16.1.2 (49151)
网络修复
 
## section 1
 1. 找到目录/Library/Preferences/Parallels/network.desktop.xml
 2. 在文件中查询`<UseKextless>1</UseKextless>` (也可能是-1), 修改值为`<UseKextless>0</UseKextless>`
 3. 如果找不到对应的tag也可以在`<ParallelsNetworkConfig>新建</ParallelsNetworkConfig>`


## section 2
USB 修复

1. /Library/Preferences/Parallels/dispatcher.desktop.xml
2. `<Usb>0</Usb>` ==>> `<Usb>1</Usb>`


**结果：您可以在没有sudo的情况下启动/重新启动Parallels –网络、USB正常工作。**
