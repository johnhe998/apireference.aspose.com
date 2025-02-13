---
title: MailMerge.MergeWholeDocument
second_title: Aspose.Words for .NET API 参考
description: MailMerge 财产. 获取或设置一个值该值指示在执行与区域的邮件合并时是否更新整个文档中的字段
type: docs
weight: 70
url: /zh/net/aspose.words.mailmerging/mailmerge/mergewholedocument/
---
## MailMerge.MergeWholeDocument property

获取或设置一个值，该值指示在执行与区域的邮件合并时是否更新整个文档中的字段。

```csharp
public bool MergeWholeDocument { get; set; }
```

### 评论

默认值为 **错误的**.

### 例子

显示邮件与区域合并和字段更新之间的关系。

```csharp
public void MergeWholeDocument(bool mergeWholeDocument)
{
    Document doc = CreateSourceDocMergeWholeDocument();
    DataTable dataTable = CreateSourceTableMergeWholeDocument();

    // 如果我们将“MergeWholeDocument”标志设置为“true”，
    // 与区域的邮件合并将更新文档中的每个字段。
    // 如果我们将“MergeWholeDocument”标志设置为“false”，邮件合并只会更新字段
    // 在名称与数据源表名称匹配的邮件合并区域内。
    doc.MailMerge.MergeWholeDocument = mergeWholeDocument;
    doc.MailMerge.ExecuteWithRegions(dataTable);

    // 邮件合并只会更新邮件合并区域外的QUOTE字段
    // 如果我们将“MergeWholeDocument”标志设置为“true”。
    doc.Save(ArtifactsDir + "MailMerge.MergeWholeDocument.docx");

    Assert.True(doc.GetText().Contains("This QUOTE field is inside the \"MyTable\" merge region."));
    Assert.AreEqual(mergeWholeDocument, 
        doc.GetText().Contains("This QUOTE field is outside of the \"MyTable\" merge region."));
}

/// <summary>
/// 创建一个包含属于名为“MyTable”的数据源的邮件合并区域的文档。
/// 在该区域内插入一个 QUOTE 字段，在区域外再插入一个。
/// </summary>
private static Document CreateSourceDocMergeWholeDocument()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    FieldQuote field = (FieldQuote)builder.InsertField(FieldType.FieldQuote, true);
    field.Text = "This QUOTE field is outside of the \"MyTable\" merge region.";

    builder.InsertParagraph();
    builder.InsertField(" MERGEFIELD TableStart:MyTable");

    field = (FieldQuote)builder.InsertField(FieldType.FieldQuote, true);
    field.Text = "This QUOTE field is inside the \"MyTable\" merge region.";
    builder.InsertParagraph();

    builder.InsertField(" MERGEFIELD MyColumn");
    builder.InsertField(" MERGEFIELD TableEnd:MyTable");

    return doc;
}

/// <summary>
/// 创建将在邮件合并中使用的数据表。
/// </summary>
private static DataTable CreateSourceTableMergeWholeDocument()
{
    DataTable dataTable = new DataTable("MyTable");
    dataTable.Columns.Add("MyColumn");
    dataTable.Rows.Add(new object[] { "MyValue" });

    return dataTable;
}
```

### 也可以看看

* class [MailMerge](../)
* 命名空间 [Aspose.Words.MailMerging](../../mailmerge/)
* 部件 [Aspose.Words](../../../)


