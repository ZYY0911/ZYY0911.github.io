---
layout: post
title: Android ReatingBar 自定义样式
subheading: 
    Android开发
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
tags: Android ReationgBar
sidebar: []
---

## 素材文件
<img src="https://img-blog.csdnimg.cn/20200812185532156.png"   width="20%">
1、首先在drawable中新建xml文件

```java
<?xml version="1.0" encoding="utf-8"?>
<layer-list xmlns:android="http://schemas.android.com/apk/res/android">
    <item
        android:id="@android:id/background"
        android:drawable="@mipmap/yuan3" />
        <!--次要进展-->
    <item
        android:id="@android:id/secondaryProgress"
        android:drawable="@mipmap/yuan3" />
    <item
        android:id="@android:id/progress"
        android:drawable="@mipmap/yuan4" />

</layer-list>
```
## 2、在style中添加样式

```java
   <style name="rating_bar_style">
        <item name="android:minHeight">50dp</item>
        <item name="android:maxHeight">50dp</item>
        <item name="android:progressDrawable">@drawable/rating</item>
    </style>

```
## 3、在布局文件中引用syle样式

```java
				<RatingBar
                    android:id="@+id/rating_bar"
                    style="@style/rating_bar_style"
                    android:layout_width="wrap_content"
                    android:layout_height="wrap_content"
                    android:layout_margin="10dp"
                    android:isIndicator="true"
                    android:numStars="5"
                    android:stepSize="0.5" />
```
android:isIndicator="true"是否只展示 ，展示不可点击


**最终效果**
<img src ="https://img-blog.csdnimg.cn/20200812185721365.png" width="40%"/>

