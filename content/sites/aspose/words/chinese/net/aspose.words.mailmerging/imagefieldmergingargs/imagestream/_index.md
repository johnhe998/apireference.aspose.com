---
title: ImageFieldMergingArgs.ImageStream
second_title: Aspose.Words for .NET API 参考
description: ImageFieldMergingArgs 财产. 指定邮件合并引擎从中读取图像的流
type: docs
weight: 40
url: /zh/net/aspose.words.mailmerging/imagefieldmergingargs/imagestream/
---
## ImageFieldMergingArgs.ImageStream property

指定邮件合并引擎从中读取图像的流。

```csharp
public Stream ImageStream { get; set; }
```

### 评论

Aspose.Words 在将图像合并到文档后关闭此流。

### 例子

演示如何将存储在数据库 BLOB 字段中的图像插入到报表中。

```csharp
public void ImageFromBlob()
{
    Document doc = new Document(MyDir + "Mail merge destination - Northwind employees.docx");

    doc.MailMerge.FieldMergingCallback = new HandleMergeImageFieldFromBlob();

    string connString = $"Provider=Microsoft.Jet.OLEDB.4.0;Data Source={DatabaseDir + "Northwind.mdb"};";
    string query = "SELECT FirstName, LastName, Title, Address, City, Region, Country, PhotoBLOB FROM Employees";

    using (OleDbConnection conn = new OleDbConnection(connString))
    {
        conn.Open();

        // 打开数据读取器，它需要处于一次读取所有记录的模式。
        OleDbCommand cmd = new OleDbCommand(query, conn);
        IDataReader dataReader = cmd.ExecuteReader();

        doc.MailMerge.ExecuteWithRegions(dataReader, "Employees");
    }

    doc.Save(ArtifactsDir + "MailMergeEvent.ImageFromBlob.docx");

private class HandleMergeImageFieldFromBlob : IFieldMergingCallback
{
    void IFieldMergingCallback.FieldMerging(FieldMergingArgs args)
    {
        // 没做什么。
    }

    /// <summary>
    /// 当邮件合并在文档中遇到名称中带有“Image:”标签的 MERGEFIELD 时调用。
    /// </summary>
    void IFieldMergingCallback.ImageFieldMerging(ImageFieldMergingArgs e)
    {
        MemoryStream imageStream = new MemoryStream((byte[])e.FieldValue);
        e.ImageStream = imageStream;
    }
}
```

### 也可以看看

* class [ImageFieldMergingArgs](../)
* 命名空间 [Aspose.Words.MailMerging](../../imagefieldmergingargs/)
* 部件 [Aspose.Words](../../../)


