---
title: Enum MailMergeCheckErrors
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Settings.MailMergeCheckErrors 枚举. 指定 Microsoft Word 将如何报告在邮件合并期间检测到的错误
type: docs
weight: 5510
url: /zh/net/aspose.words.settings/mailmergecheckerrors/
---
## MailMergeCheckErrors enumeration

指定 Microsoft Word 将如何报告在邮件合并期间检测到的错误。

```csharp
public enum MailMergeCheckErrors
```

### 价值观

| 姓名 | 价值 | 描述 |
| --- | --- | --- |
| Simulate | `1` | 在新文档中模拟合并报错。 |
| PauseOnError | `2` | 完成合并并暂停报告错误。 |
| CollectErrors | `3` | 在新文档中完成合并并报告错误。 |
| Default | `2` | 等于PauseOnError值. |

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

* property [CheckErrors](../mailmergesettings/checkerrors/)
* 命名空间 [Aspose.Words.Settings](../../aspose.words.settings/)
* 部件 [Aspose.Words](../../)


