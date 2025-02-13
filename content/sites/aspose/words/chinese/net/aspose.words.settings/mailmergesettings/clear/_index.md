---
title: MailMergeSettings.Clear
second_title: Aspose.Words for .NET API 参考
description: MailMergeSettings 方法. 清除邮件合并设置这样当保存文档时 不会保存邮件合并设置它会变成一个普通的文档
type: docs
weight: 180
url: /zh/net/aspose.words.settings/mailmergesettings/clear/
---
## MailMergeSettings.Clear method

清除邮件合并设置，这样当保存文档时 不会保存邮件合并设置，它会变成一个普通的文档。

```csharp
public void Clear()
```

### 例子

显示如何在连接到外部数据源时执行邮件合并。

```csharp
Document doc = new Document(MyDir + "Odso data.docx");
MailMergeSettings settings = doc.MailMergeSettings;

Console.WriteLine($"Connection string:\n\t{settings.ConnectString}");
Console.WriteLine($"Mail merge docs as attachment:\n\t{settings.MailAsAttachment}");
Console.WriteLine($"Mail merge doc e-mail subject:\n\t{settings.MailSubject}");
Console.WriteLine($"Column that contains e-mail addresses:\n\t{settings.AddressFieldName}");
Console.WriteLine($"Active record:\n\t{settings.ActiveRecord}");

Odso odso = settings.Odso;

Console.WriteLine($"File will connect to data source located in:\n\t\"{odso.DataSource}\"");
Console.WriteLine($"Source type:\n\t{odso.DataSourceType}");
Console.WriteLine($"UDL connection string:\n\t{odso.UdlConnectString}");
Console.WriteLine($"Table:\n\t{odso.TableName}");
Console.WriteLine($"Query:\n\t{doc.MailMergeSettings.Query}");

// 我们可以通过清除它们来重置这些设置。一旦我们这样做并保存文档，
// 当我们使用它加载文档时，Microsoft Word 将不再执行邮件合并。
settings.Clear();

doc.Save(ArtifactsDir + "MailMerge.OdsoEmail.docx");
```

### 也可以看看

* class [MailMergeSettings](../)
* 命名空间 [Aspose.Words.Settings](../../mailmergesettings/)
* 部件 [Aspose.Words](../../../)


