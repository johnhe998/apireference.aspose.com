---
title: Enum MailMergeCleanupOptions
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.MailMerging.MailMergeCleanupOptions 枚举. 指定确定在邮件合并期间删除哪些项目的选项
type: docs
weight: 3630
url: /zh/net/aspose.words.mailmerging/mailmergecleanupoptions/
---
## MailMergeCleanupOptions enumeration

指定确定在邮件合并期间删除哪些项目的选项。

```csharp
[Flags]
public enum MailMergeCleanupOptions
```

### 价值观

| 姓名 | 价值 | 描述 |
| --- | --- | --- |
| None | `0` | 指定默认值。 |
| RemoveEmptyParagraphs | `1` | 指定是否应从文档中删除包含没有数据的邮件合并字段的段落。 设置此选项时，包含区域开始和结束合并字段的段落也会被删除，否则它们为空 。 |
| RemoveUnusedRegions | `2` | 指定是否应从文档中删除未使用的邮件合并区域。 |
| RemoveUnusedFields | `4` | 指定是否应从文档中删除未使用的合并字段。 |
| RemoveContainingFields | `8` | 指定如果嵌套的合并字段被删除，是否应从文档中删除包含合并字段（例如，IF）的字段 。 |
| RemoveStaticFields | `10` | 指定是否应从文档中删除静态字段。静态字段是字段，which 结果在任何文档更改时保持不变。字段，不将其结果存储在 document 中并且是动态计算的（例如FieldListNum , FieldSymbol等）不被认为是静态的。 |
| RemoveEmptyTableRows | `20` | 指定是否应从文档中删除包含邮件合并区域的空行。 |

### 例子

演示如何从合并输出文档中删除邮件合并可能创建的空段落。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(" MERGEFIELD TableStart:MyTable");
builder.InsertField(" MERGEFIELD FirstName ");
builder.Write(" ");
builder.InsertField(" MERGEFIELD LastName ");
builder.InsertField(" MERGEFIELD TableEnd:MyTable");

DataTable dataTable = new DataTable("MyTable");
dataTable.Columns.Add("FirstName");
dataTable.Columns.Add("LastName");
dataTable.Rows.Add(new object[] { "John", "Doe" });
dataTable.Rows.Add(new object[] { "", "" });
dataTable.Rows.Add(new object[] { "Jane", "Doe" });

doc.MailMerge.CleanupOptions = mailMergeCleanupOptions;
doc.MailMerge.ExecuteWithRegions(dataTable);

if (doc.MailMerge.CleanupOptions == MailMergeCleanupOptions.RemoveEmptyParagraphs) 
    Assert.AreEqual(
        "John Doe\r" +
        "Jane Doe", doc.GetText().Trim());
else
    Assert.AreEqual(
        "John Doe\r" +
        " \r" +
        "Jane Doe", doc.GetText().Trim());
```

显示如何自动删除邮件合并期间未使用的 MERGEFIELD。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 为邮件合并数据源表的三列创建一个带有 MERGEFIELD 的文档，
// 然后创建一个只有两列名称与我们的 MERGEFIELD 匹配的表。
builder.InsertField(" MERGEFIELD FirstName ");
builder.Write(" ");
builder.InsertField(" MERGEFIELD LastName ");
builder.InsertParagraph();
builder.InsertField(" MERGEFIELD City ");

DataTable dataTable = new DataTable("MyTable");
dataTable.Columns.Add("FirstName");
dataTable.Columns.Add("LastName");
dataTable.Rows.Add(new object[] { "John", "Doe" });
dataTable.Rows.Add(new object[] { "Joe", "Bloggs" });

// 我们的第三个 MERGEFIELD 引用了一个“城市”列，该列在我们的数据源中不存在。
// 邮件合并会将诸如此类的字段保持在合并前的状态。
// 将“CleanupOptions”属性设置为“RemoveUnusedFields”将删除所有 MERGEFIELD
// 在邮件合并期间未使用以清理合并文档。
doc.MailMerge.CleanupOptions = mailMergeCleanupOptions;
doc.MailMerge.Execute(dataTable);

if (mailMergeCleanupOptions == MailMergeCleanupOptions.RemoveUnusedFields || 
    mailMergeCleanupOptions == MailMergeCleanupOptions.RemoveStaticFields)
    Assert.AreEqual(0, doc.Range.Fields.Count);
else
    Assert.AreEqual(2, doc.Range.Fields.Count);
```

### 也可以看看

* 命名空间 [Aspose.Words.MailMerging](../../aspose.words.mailmerging/)
* 部件 [Aspose.Words](../../)


