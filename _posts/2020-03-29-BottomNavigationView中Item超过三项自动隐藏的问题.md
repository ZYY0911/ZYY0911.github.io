---
layout: post
title: Android BottomNavigationView中Item超过三项自动隐藏的问题
subtitle: MacBook
categories: markdown
author: 老八
categories: zyy
tags: Android BottomNavigationView
---

<img src="https://img-blog.csdnimg.cn/20200329190411377.jpg"   width="40%">
<img src="https://img-blog.csdnimg.cn/2020032919042910.jpg"   width="40%">

```java
 <android.support.design.widget.BottomNavigationView
            android:id="@+id/bottom_nva"
            android:layout_width="match_parent"
            android:layout_height="0dp"
            android:layout_weight="1"
            app:menu="@menu/nav_bottom2">
</android.support.design.widget.BottomNavigationView>
```

```java
<?xml version="1.0" encoding="utf-8"?>
<menu xmlns:android="http://schemas.android.com/apk/res/android">
    <item
        android:id="@+id/navigation_kc"
        android:icon="@mipmap/ic_comment"
        android:title="库存" />
    <item
        android:id="@+id/navigation_yj"
        android:icon="@mipmap/nav_mail"
        android:title="预警" />

    <item
        android:id="@+id/navigation_rk"
        android:icon="@mipmap/nav_location"
        android:title="入库" />

    <item
        android:id="@+id/navigation_ck"
        android:icon="@mipmap/nav_friends"
        android:title="出库" />
</menu>
```
解决代码

```java
protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        bottomNavigationView = findViewById(R.id.buttonNav);
        //设置bottomNavigationView
        bottomNavigationView.setLabelVisibilityMode(1);
}
```

