---
layout: post
title: C#设置DataGirdView行背景无效的问题
subheading: 
    C#开发
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
tags: C# Winform
sidebar: []
---

## C#设置DataGridView行背景色无效的问题
设置代码

```csharp
 for (int i = 0; i < dataGridView1.RowCount; i++)
 {
      if (i % 2 == 0)
      {
           dataGridView1.Rows[i].DefaultCellStyle.BackColor = Color.SeaGreen;
      }
      else
      {
            dataGridView1.Rows[i].DefaultCellStyle.BackColor = Color.Khaki;
      }
}
```
解决办法 在DataGridView中找到属性窗口添加 RowPrePaint事件
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200329175832613.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MzgyNjEwOQ==,size_16,color_FFFFFF,t_70#pic_center)
再将设置颜色的代码写到RowPrePaint事件中

```csharp
private void dataGridView1_RowPrePaint(object sender, DataGridViewRowPrePaintEventArgs e)
{
    for (int i = 0; i < dataGridView1.RowCount; i++)
    {
        if (i % 2 == 0)
        {
            dataGridView1.Rows[i].DefaultCellStyle.BackColor = Color.SeaGreen;
        }
        else
        {
            dataGridView1.Rows[i].DefaultCellStyle.BackColor = Color.Khaki;
        }
    }
}
```
微软官方文档
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200329180058606.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MzgyNjEwOQ==,size_16,color_FFFFFF,t_70#pic_center)

