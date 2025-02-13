---
title: MailMergeSettings.HeaderSource
second_title: Aspose.Words für .NET-API-Referenz
description: MailMergeSettings eigendom. Gibt den Pfad zur Quelle des SeriendruckHeaders an. Der Standardwert ist eine leere Zeichenfolge.
type: docs
weight: 100
url: /de/net/aspose.words.settings/mailmergesettings/headersource/
---
## MailMergeSettings.HeaderSource property

Gibt den Pfad zur Quelle des Seriendruck-Headers an. Der Standardwert ist eine leere Zeichenfolge.

```csharp
public string HeaderSource { get; set; }
```

### Beispiele

Zeigt, wie eine Datenquelle für einen Seriendruck aus einer Kopfzeilenquelle und einer Datenquelle erstellt wird.

```csharp
// Erstellen Sie eine Kopfzeilendatei für das Zusammenführen von Adressetiketten, die aus einer Tabelle mit einer Zeile besteht.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.StartTable();
builder.InsertCell();
builder.Write("FirstName");
builder.InsertCell();
builder.Write("LastName");
builder.EndTable();

doc.Save(ArtifactsDir + "MailMerge.MailingLabelMerge.Header.docx");

// Erstellen Sie eine Zusammenführungsdatendatei für Adressetiketten, die aus einer Tabelle mit einer Zeile besteht
// und die gleiche Anzahl von Spalten wie die Tabelle des Header-Dokuments. 
doc = new Document();
builder = new DocumentBuilder(doc);

builder.StartTable();
builder.InsertCell();
builder.Write("John");
builder.InsertCell();
builder.Write("Doe");
builder.EndTable();

doc.Save(ArtifactsDir + "MailMerge.MailingLabelMerge.Data.docx");

// Erstellen Sie ein Zusammenführungszieldokument mit MERGEFIELDS mit Namen, die
// die Spaltennamen in der Header-Dateitabelle der Zusammenführung abgleichen.
doc = new Document();
builder = new DocumentBuilder(doc);

builder.Write("Dear ");
builder.InsertField("MERGEFIELD FirstName", "<FirstName>");
builder.Write(" ");
builder.InsertField("MERGEFIELD LastName", "<LastName>");

MailMergeSettings settings = doc.MailMergeSettings;

// Erstellen Sie eine Datenquelle für unseren Seriendruck, indem Sie zwei Dokumentdateinamen angeben.
// Die Header-Quelle benennt die Spalten der Datenquellentabelle.
settings.HeaderSource = ArtifactsDir + "MailMerge.MailingLabelMerge.Header.docx";

// Die Datenquelle stellt Datenzeilen für alle Spalten in der Header-Dokumenttabelle bereit.
settings.DataSource = ArtifactsDir + "MailMerge.MailingLabelMerge.Data.docx";

// Konfigurieren Sie einen Seriendruck vom Typ Adressetikett, der von Microsoft Word ausgeführt wird
// sobald wir damit das Ausgabedokument laden.
settings.Query = "SELECT * FROM " + settings.DataSource;
settings.MainDocumentType = MailMergeMainDocumentType.MailingLabels;
settings.DataType = MailMergeDataType.TextFile;
settings.LinkToQuery = true;
settings.ViewMergedData = true;

doc.Save(ArtifactsDir + "MailMerge.MailingLabelMerge.docx");
```

### Siehe auch

* class [MailMergeSettings](../)
* namensraum [Aspose.Words.Settings](../../mailmergesettings/)
* Montage [Aspose.Words](../../../)


