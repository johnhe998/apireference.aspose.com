---
title: MailMergeSettings.Odso
second_title: Aspose.Words för .NET API Referens
description: MailMergeSettings fast egendom. Hämtar eller ställer in objektet som anger ODSOinställningarna Office Data Source Object.
type: docs
weight: 150
url: /sv/net/aspose.words.settings/mailmergesettings/odso/
---
## MailMergeSettings.Odso property

Hämtar eller ställer in objektet som anger ODSO-inställningarna (Office Data Source Object).

```csharp
public Odso Odso { get; set; }
```

### Anmärkningar

Detta objekt är aldrig null.

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

* class [Odso](../../odso/)
* class [MailMergeSettings](../)
* namnutrymme [Aspose.Words.Settings](../../mailmergesettings/)
* hopsättning [Aspose.Words](../../../)


