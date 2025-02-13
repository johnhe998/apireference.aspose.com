---
title: MailMerge.UnconditionalMergeFieldsAndRegions
second_title: Aspose.Words for .NET API 参考
description: MailMerge 财产. 获取或设置一个值该值指示是否合并合并字段和合并区域而不考虑父 IF 字段的条件
type: docs
weight: 140
url: /zh/net/aspose.words.mailmerging/mailmerge/unconditionalmergefieldsandregions/
---
## MailMerge.UnconditionalMergeFieldsAndRegions property

获取或设置一个值，该值指示是否合并合并字段和合并区域，而不考虑父 IF 字段的条件。

```csharp
public bool UnconditionalMergeFieldsAndRegions { get; set; }
```

### 评论

默认值为 **错误的**.

### 例子

显示如何合并字段或区域，而不考虑父 IF 字段的条件。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 插入嵌套在 IF 字段中的 MERGEFIELD。
// 由于IF字段语句为false，所以不会显示MERGEFIELD的结果。
// MERGEFIELD 在邮件合并期间也不会收到任何数据。
FieldIf fieldIf = (FieldIf)builder.InsertField(" IF 1 = 2 ");
builder.MoveTo(fieldIf.Separator);
builder.InsertField(" MERGEFIELD  FullName ");

// 如果我们将“UnconditionalMergeFieldsAndRegions”标志设置为“true”，
// 我们的邮件合并会将数据插入到未显示的字段中，例如我们的 MERGEFIELD 以及所有其他字段。
// 如果我们将“UnconditionalMergeFieldsAndRegions”标志设置为“false”，
// 我们的邮件合并不会将数据插入到被带有错误语句的 IF 字段隐藏的 MERGEFIELD 中。
doc.MailMerge.UnconditionalMergeFieldsAndRegions = countAllMergeFields;

DataTable dataTable = new DataTable();
dataTable.Columns.Add("FullName");
dataTable.Rows.Add("James Bond");

doc.MailMerge.Execute(dataTable);

doc.Save(ArtifactsDir + "MailMerge.UnconditionalMergeFieldsAndRegions.docx");

Assert.AreEqual(
    countAllMergeFields
        ? "\u0013 IF 1 = 2 \"James Bond\"\u0014\u0015"
        : "\u0013 IF 1 = 2 \u0013 MERGEFIELD  FullName \u0014«FullName»\u0015\u0014\u0015",
    doc.GetText().Trim());
```

### 也可以看看

* class [MailMerge](../)
* 命名空间 [Aspose.Words.MailMerging](../../mailmerge/)
* 部件 [Aspose.Words](../../../)


