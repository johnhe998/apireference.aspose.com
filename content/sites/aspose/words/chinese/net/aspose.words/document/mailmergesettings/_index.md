---
title: Document.MailMergeSettings
second_title: Aspose.Words for .NET API 参考
description: Document 财产. 获取或设置包含文档的所有邮件合并信息的对象
type: docs
weight: 250
url: /zh/net/aspose.words/document/mailmergesettings/
---
## Document.MailMergeSettings property

获取或设置包含文档的所有邮件合并信息的对象。

```csharp
public MailMergeSettings MailMergeSettings { get; set; }
```

### 评论

您可以使用此对象为文档指定邮件合并数据源，当用户打开此文档时，此信息 （以及可用的数据字段）将出现在 Microsoft Word 中。 或者您可以使用此对象查询邮件合并设置用户已在 Microsoft Word 中为此文档指定。

该对象永远不会为空。

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

* class [MailMergeSettings](../../../aspose.words.settings/mailmergesettings/)
* class [Document](../)
* 命名空间 [Aspose.Words](../../document/)
* 部件 [Aspose.Words](../../../)


