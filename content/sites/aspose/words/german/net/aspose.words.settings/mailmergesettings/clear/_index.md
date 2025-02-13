---
title: MailMergeSettings.Clear
second_title: Aspose.Words für .NET-API-Referenz
description: MailMergeSettings methode. Löscht die Serienbriefeinstellungen so dass beim Speichern des Dokuments keine Serienbriefeinstellungen gespeichert werden und es zu einem normalen Dokument wird.
type: docs
weight: 180
url: /de/net/aspose.words.settings/mailmergesettings/clear/
---
## MailMergeSettings.Clear method

Löscht die Serienbriefeinstellungen so, dass beim Speichern des Dokuments keine Serienbriefeinstellungen gespeichert werden und es zu einem normalen Dokument wird.

```csharp
public void Clear()
```

### Beispiele

Zeigt, wie ein Seriendruck ausgeführt wird, während eine Verbindung zu einer externen Datenquelle hergestellt wird.

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

// Wir können diese Einstellungen zurücksetzen, indem wir sie löschen. Sobald wir das getan und das Dokument gespeichert haben,
// Microsoft Word führt keinen Seriendruck mehr aus, wenn wir es zum Laden des Dokuments verwenden.
settings.Clear();

doc.Save(ArtifactsDir + "MailMerge.OdsoEmail.docx");
```

### Siehe auch

* class [MailMergeSettings](../)
* namensraum [Aspose.Words.Settings](../../mailmergesettings/)
* Montage [Aspose.Words](../../../)


