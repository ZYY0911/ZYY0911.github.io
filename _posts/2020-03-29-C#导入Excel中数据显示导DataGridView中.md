---
layout: post
title: C#导入Excel中数据显示导DataGridView中
subtitle: Windows
categories: markdown
author: 老八
categories: zyy
tags: Windows Winform Excel 窗体
---

## C#导入Excel中数据显示导DataGridView中

```csharp
private void button1_Click(object sender, EventArgs e)
{
    OpenFileDialog fileDialog = new OpenFileDialog();
    fileDialog.Filter = "所有文件(*.*)|*.*|Excel 97-2003工作薄(*.xls)|*.xls|Excel 工作薄(*.xlsx)|*.xlsx";
    fileDialog.FileName = "";
    string path = "";
    if (fileDialog.ShowDialog() == DialogResult.OK)
    {
        path = fileDialog.FileName;
    }
    if (path == "")
    {
        MessageBox.Show("没有选择Excel文件，无法导入");
        return;
    }
    label1.Text = path;
    dataGridView1.DataSource = ReadExcelToTable(path);
}
private static DataTable ReadExcelToTable(string path)
{
    try
    {
        string FileType = path.Substring(path.LastIndexOf('.'));
        string connsring = "";
        if (FileType == ".xls")
            connsring = "Provider=Microsoft.Jet.OLEDB.4.0;" +
            "Data Source=" + path + ";Extended Properties=Excel 8.0;";
        else//.xlsx  
            connsring = "Provider=Microsoft.ACE.OLEDB.12.0;Data Source=" + path + ";Extended Properties='Excel 12.0;HDR=YES;IMEX=1'";
        OleDbConnection connection = new OleDbConnection(connsring);
        connection.Open();
        //GetOleDbSchemaTable取出来的不一定是默认顺序。。。。。。怎么解决暂时没有办法
        DataTable sheetsNames = connection.GetOleDbSchemaTable(OleDbSchemaGuid.Tables
            , new object[] { null, null, null, "TABLE" });//得到所有sheet的名字
        string fitstSheetName = sheetsNames.Rows[0][2].ToString();//得到第一个sheet名字
        string sql = string.Format("select * from[{0}]", fitstSheetName);
        OleDbDataAdapter adapter = new OleDbDataAdapter(sql, connsring);
        DataSet data = new DataSet();
        adapter.Fill(data);
        connection.Close();
        Console.WriteLine(data.Tables[0].Rows[0][0].ToString());
        return data.Tables[0];
    }
    catch (Exception)
    {
        return null;
    }
}
```

