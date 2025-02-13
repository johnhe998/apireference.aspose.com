---
title: Enum OdsoDataSourceType
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Settings.OdsoDataSourceType 枚举. 指定要连接到的外部数据源的类型作为 ODSO 连接信息的一部分
type: docs
weight: 5590
url: /zh/net/aspose.words.settings/odsodatasourcetype/
---
## OdsoDataSourceType enumeration

指定要连接到的外部数据源的类型，作为 ODSO 连接信息的一部分。

```csharp
public enum OdsoDataSourceType
```

### 价值观

| 姓名 | 价值 | 描述 |
| --- | --- | --- |
| Text | `0` | 指定给定文档已连接到文本文件。 可能是 wdMergeSubTypeOther。 |
| Database | `1` | 指定给定文档已连接到数据库。 可能是 wdMergeSubTypeAccess。 |
| AddressBook | `2` | 指定给定文档已连接到联系人地址簿。 可能是 wdMergeSubTypeOAL。 |
| Document1 | `3` | 指定给定文档已连接到生成应用程序支持的另一种文档格式。 可能是 wdMergeSubTypeOLEDBWord。 |
| Document2 | `4` | 指定给定文档已连接到生成应用程序支持的另一种文档格式。 可能是 wdMergeSubTypeWorks。 |
| Native | `5` | 指定给定文档已连接到生成应用程序本机的另一种文档格式。 可能是 wdMergeSubTypeOLEDBText |
| Email | `6` | 指定给定文档已连接到电子邮件应用程序。 可能是 wdMergeSubTypeOutlook。 |
| None | `7` | 未指定外部数据源的类型。 可能是wdMergeSubTypeWord。 |
| Legacy | `8` | 指定给定文档已连接到生产应用程序支持的旧文档格式 可能是 wdMergeSubTypeWord2000. |
| Master | `9` | 指定给定文档已连接到聚合其他数据源的数据源。 |
| Default | `7` | 等于None. |

### 评论

OOXML 规范对于这个枚举非常模糊。我猜它可能对应于 WdMergeSubType 枚举 http://msdn.microsoft.com/en-us/library/bb237801.aspx。

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

* 命名空间 [Aspose.Words.Settings](../../aspose.words.settings/)
* 部件 [Aspose.Words](../../)


