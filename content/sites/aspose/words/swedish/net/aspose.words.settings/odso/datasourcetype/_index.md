---
title: Odso.DataSourceType
second_title: Aspose.Words för .NET API Referens
description: Odso fast egendom. Anger typen av den externa datakällan som ska anslutas till som en del av ODSOanslutningsinformationen för denna koppling. Standardvärdet ärDefault .
type: docs
weight: 40
url: /sv/net/aspose.words.settings/odso/datasourcetype/
---
## Odso.DataSourceType property

Anger typen av den externa datakällan som ska anslutas till som en del av ODSO-anslutningsinformationen för denna koppling. Standardvärdet ärDefault .

```csharp
public OdsoDataSourceType DataSourceType { get; set; }
```

### Anmärkningar

Den här inställningen är enbart ett förslag på datakällans typ som används för den här kopplingen.

### Exempel

Visar hur man kör en sammankoppling med data från ett Office-datakällobjekt.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Dear ");
builder.InsertField("MERGEFIELD FirstName", "<FirstName>");
builder.Write(" ");
builder.InsertField("MERGEFIELD LastName", "<LastName>");
builder.Writeln(": ");
builder.InsertField("MERGEFIELD Message", "<Message>");

// Skapa en datakälla i form av en ASCII-fil, med "|" karaktär
// fungerar som avgränsaren som separerar kolumner. Den första raden innehåller de tre kolumnernas namn,
// och varje efterföljande rad är en rad med sina respektive värden.
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

// Att öppna detta dokument i Microsoft Word kommer att köra sammanslagningen innan innehållet visas. 
doc.Save(ArtifactsDir + "MailMerge.MailMergeSettings.docx");
```

### Se även

* enum [OdsoDataSourceType](../../odsodatasourcetype/)
* class [Odso](../)
* namnutrymme [Aspose.Words.Settings](../../odso/)
* hopsättning [Aspose.Words](../../../)


