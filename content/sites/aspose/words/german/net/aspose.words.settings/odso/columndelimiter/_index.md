---
title: Odso.ColumnDelimiter
second_title: Aspose.Words für .NET-API-Referenz
description: Odso eigendom. Gibt das Zeichen an das als Spaltentrennzeichen interpretiert werden soll das verwendet wird um Spalten innerhalb externer Datenquellen zu trennen. Der Standardwert ist 0 was bedeutet dass kein Spaltentrennzeichen definiert ist.
type: docs
weight: 20
url: /de/net/aspose.words.settings/odso/columndelimiter/
---
## Odso.ColumnDelimiter property

Gibt das Zeichen an, das als Spaltentrennzeichen interpretiert werden soll, das verwendet wird, um Spalten innerhalb externer Datenquellen zu trennen. Der Standardwert ist 0, was bedeutet, dass kein Spaltentrennzeichen definiert ist.

```csharp
public char ColumnDelimiter { get; set; }
```

### Bemerkungen

RK Ich habe das noch nie im Einsatz gesehen.

### Beispiele

Zeigt, wie ein Seriendruck mit Daten aus einem Office-Datenquellenobjekt ausgeführt wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Dear ");
builder.InsertField("MERGEFIELD FirstName", "<FirstName>");
builder.Write(" ");
builder.InsertField("MERGEFIELD LastName", "<LastName>");
builder.Writeln(": ");
builder.InsertField("MERGEFIELD Message", "<Message>");

// Erstellen Sie eine Datenquelle in Form einer ASCII-Datei, mit dem "|" Charakter
// fungiert als Trennzeichen, das Spalten trennt. Die erste Zeile enthält die Namen der drei Spalten,
// und jede nachfolgende Zeile ist eine Zeile mit ihren jeweiligen Werten.
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

// Beim Öffnen dieses Dokuments in Microsoft Word wird der Seriendruck ausgeführt, bevor der Inhalt angezeigt wird. 
doc.Save(ArtifactsDir + "MailMerge.MailMergeSettings.docx");
```

### Siehe auch

* class [Odso](../)
* namensraum [Aspose.Words.Settings](../../odso/)
* Montage [Aspose.Words](../../../)


