---
layout: post
title: Mac下开启Tomcat服务器
subheading: 
    Mac终端
author: 老八
categories: zyy
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
tags: Mac Command
sidebar: []
---
# Mac下开启Tomcat服务器

首先确保你的电脑已经安装了JDK
可以在终端内输入 java -version 确保出现出现以下信息（不用版本可能会有所不同）![在这里插入图片描述](https://img-blog.csdnimg.cn/20200329113339488.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MzgyNjEwOQ==,size_16,color_FFFFFF,t_70#pic_center)
把下载好的tomact压缩包解压到电脑中（我这里习惯放到个人文件夹内）
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200329113910826.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MzgyNjEwOQ==,size_16,color_FFFFFF,t_70#pic_center)
这里可以给解压出来的文件重命名一下![在这里插入图片描述](https://img-blog.csdnimg.cn/20200329114046682.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MzgyNjEwOQ==,size_16,color_FFFFFF,t_70#pic_center)
打开Mac电脑中的终端输入命令 cd /Users/zhangyingyu/tomcat_ver8/bin  回车在输入
sudo sh startup.sh 在回车 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20200329114710636.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MzgyNjEwOQ==,size_16,color_FFFFFF,t_70#pic_center)
会看到需要输入Password （输入你的开机密码，再次输入看不见输入内容，不要输错 ，输入完后回车）出现一下提示则证明开启成功
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200329114854728.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MzgyNjEwOQ==,size_16,color_FFFFFF,t_70#pic_center) 输入sudo sh shutdown.sh---关闭Tomcat
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200329115159109.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MzgyNjEwOQ==,size_16,color_FFFFFF,t_70#pic_center)

如果需要和Windows一样输出信息 把sudo sh startup.sh  
替换成 sudo sh catalina.sh run  接下来还是需要输入密码

![在这里插入图片描述](https://img-blog.csdnimg.cn/2020032911545486.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MzgyNjEwOQ==,size_16,color_FFFFFF,t_70#pic_center)
接下来就可以看到输出窗口了
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200329115632211.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MzgyNjEwOQ==,size_16,color_FFFFFF,t_70#pic_center)

