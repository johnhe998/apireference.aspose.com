---
title: Enum MailMergeDestination
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Settings.MailMergeDestination 枚举. 指定对文档执行邮件合并时可能产生的结果
type: docs
weight: 5530
url: /zh/net/aspose.words.settings/mailmergedestination/
---
## MailMergeDestination enumeration

指定对文档执行邮件合并时可能产生的结果。

```csharp
public enum MailMergeDestination
```

### 价值观

| 姓名 | 价值 | 描述 |
| --- | --- | --- |
| NewDocument | `0` | 指定符合要求的托管应用程序应通过使用来自指定外部数据源的数据填充给定文档中的字段 来生成新文档。 |
| Printer | `1` | 指定符合要求的托管应用程序应打印通过使用来自指定外部数据源的外部数据填充给定文档中的 字段而产生的文档。 |
| Email | `2` | 指定符合要求的托管应用程序应使用来自 使用来自指定外部数据源的数据填充给定文档中的字段的文档生成电子邮件。 |
| Fax | `4` | 指定符合要求的托管应用程序应使用产生的文档生成传真 使用来自指定外部数据源的数据填充给定文档中的字段。 |
| Default | `0` | 等于NewDocument值. |

### 例子

演示如何使用 Office 数据源对象中的数据执行邮件合并。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Dear ");
builder.InsertField("MERGEFIELD FirstName", "<FirstName>");
builder.Write(" ");
builder.InsertField("MERGEFIELD LastName", "<LastName>");
builder.Writeln(": ");
builder.InsertField("MERGEFIELD Message", "<Message>");

// 创建一个ASCII文件形式的数据源，用“|”特点
// 充当分隔列的分隔符。第一行包含三列的名称，
// 之后的每一行都是具有各自值的行。
string[] lines = { "FirstName|LastName|Message",
    "John|Doe|Hello! This message was created with Aspose Words mail merge." };
string dataSrcFilename = ArtifactsDir + "MailMerge.MailMergeSettings.DataSource.txt";

File.WriteAllLines(dataSrcFilename, lines);

MailMergeSettings settings = doc.MailMergeSettings;
settings.MainDocumentType = MailMergeMainDocumentType.MailingLabels;
settings.CheckErrors = MailMergeCheckErrors.Simulate;
settings.DataType = MailMergeDataType.Native;
settings.DataSource = dataSrcFilename;
settings.Query = "SELECT * FROM " + doc.MailMergeSettings.DataSource;
settings.LinkToQuery = true;
settings.ViewMergedData = true;

Assert.AreEqual(MailMergeDestination.Default, settings.Destination);
Assert.False(settings.DoNotSupressBlankLines);

Odso odso = settings.Odso;
odso.DataSource = dataSrcFilename;
odso.DataSourceType = OdsoDataSourceType.Text;
odso.ColumnDelimiter = '|';
odso.FirstRowContainsColumnNames = true;

Assert.AreNotSame(odso, odso.Clone());
Assert.AreNotSame(settings, settings.Clone());

// 在 Microsoft Word 中打开此文档将在显示内容之前执行邮件合并。 
doc.Save(ArtifactsDir + "MailMerge.MailMergeSettings.docx");
```

### 也可以看看

* property [Destination](../mailmergesettings/destination/)
* 命名空间 [Aspose.Words.Settings](../../aspose.words.settings/)
* 部件 [Aspose.Words](../../)


