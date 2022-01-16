---
layout: post
title: C#合并两个DataTable
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
tags: C# VSCode
sidebar: []
---

## C#合并两个DataTable（两个结构一样）

```csharp
private DataTable SetDataTbble(DataTable table1,DataTable table2)
{
    DataTable dataTable = table1.Clone();
    object[] obj = new object[dataTable.Columns.Count];
    for (int i = 0; i < table1.Rows.Count; i++)
    {
        table1.Rows[i].ItemArray.CopyTo(obj, 0);
        dataTable.Rows.Add(obj);
    }
    for (int i = 0; i < table2.Rows.Count; i++)
    {
        table2.Rows[i].ItemArray.CopyTo(obj, 0);
        dataTable.Rows.Add(obj);
    }
    return dataTable;
}
```

