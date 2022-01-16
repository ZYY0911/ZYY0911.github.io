---
layout: post
title: C#将DataGridView中数据导出为Excel
subtitle: Windows
categories: markdown
author: 老八
categories: zyy
tags: Windows Winform Excel 窗体
---
# C#将DataGridView中数据导出为Excel
1、首先需要添加Microsoft Office 16.0 Object Library
2、导入引用using Excel = Microsoft.Office.Interop.Excel;
```csharp
		SaveFileDialog fileDialog = new SaveFileDialog();
        fileDialog.Filter = "Excel文件|*.xlsx|Excel(2003文件)|*.xls";
        if (fileDialog.ShowDialog() == DialogResult.OK)
        {
            string path = fileDialog.FileName;
            Excel.Application application = new Excel.Application();
            Excel.Workbooks workbooks = application.Workbooks;
            Excel.Workbook workbook = workbooks.Add(Excel.XlWBATemplate.xlWBATWorksheet);
            Excel.Worksheet worksheet = workbook.Worksheets[1];
            int colIndex = 0;
            //导出DataGridView中的标题
            for (int i = 0; i < dataGridView1.ColumnCount; i++)
            {
                if (dataGridView1.Columns[i].Visible)//做同于不导出隐藏列
                {
                    colIndex++;
                    worksheet.Cells[1, colIndex] = dataGridView1.Columns[i].HeaderText;
                }
            }
            //导出DataGridView中的数据
            for (int i = 0; i < dataGridView1.RowCount; i++)
            {
                colIndex = 0;
                for (int j = 0; j < dataGridView1.ColumnCount; j++)
                {
                    if (dataGridView1.Columns[j].Visible)
                    {
                        colIndex++;
                        worksheet.Cells[i + 2, colIndex] = "'"+dataGridView1.Rows[i].Cells[j].Value;
                    }
                }
            }
            //保存文件
            workbook.SaveAs(fileDialog.FileName);
            application.Quit();
            MessageBox.Show("导出成功");
        }
```

