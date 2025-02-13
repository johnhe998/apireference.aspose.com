---
title: Enum OdsoDataSourceType
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.Settings.OdsoDataSourceType uppräkning. Anger typen av extern datakälla som ska anslutas till som en del av ODSOanslutningsinformationen.
type: docs
weight: 5590
url: /sv/net/aspose.words.settings/odsodatasourcetype/
---
## OdsoDataSourceType enumeration

Anger typen av extern datakälla som ska anslutas till som en del av ODSO-anslutningsinformationen.

```csharp
public enum OdsoDataSourceType
```

### Värderingar

| namn | Värde | Beskrivning |
| --- | --- | --- |
| Text | `0` | Anger att ett givet dokument har kopplats till en textfil. Eventuellt wdMergeSubTypeOther. |
| Database | `1` | Anger att ett givet dokument har kopplats till en databas. Eventuellt wdMergeSubTypeAccess. |
| AddressBook | `2` | Anger att ett givet dokument har kopplats till en adressbok med kontakter. Eventuellt wdMergeSubTypeOAL. |
| Document1 | `3` | Anger att ett visst dokument har kopplats till ett annat dokumentformat som stöds av det producerande programmet. Eventuellt wdMergeSubTypeOLEDBWord. |
| Document2 | `4` | Anger att ett visst dokument har kopplats till ett annat dokumentformat som stöds av det producerande programmet. Eventuellt wdMergeSubTypeWorks. |
| Native | `5` | Anger att ett visst dokument har kopplats till ett annat dokumentformat som är inbyggt i det producerande programmet. Eventuellt wdMergeSubTypeOLEDBText |
| Email | `6` | Anger att ett visst dokument har kopplats till ett e-postprogram. Eventuellt wdMergeSubTypeOutlook. |
| None | `7` | Typen för den externa datakällan är inte specificerad. Eventuellt wdMergeSubTypeWord. |
| Legacy | `8` | Anger att ett visst dokument har kopplats till ett äldre dokumentformat som stöds av det producerande programmet Eventuellt wdMergeSubTypeWord2000. |
| Master | `9` | Anger att ett visst dokument har kopplats till en datakälla som aggregerar andra datakällor. |
| Default | `7` | MotsvararNone . |

### Anmärkningar

OOXML-specifikationen är mycket vag för denna uppräkning. Jag antar att det kan motsvara WdMergeSubType -uppräkningen http://msdn.microsoft.com/en-us/library/bb237801.aspx.

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

* namnutrymme [Aspose.Words.Settings](../../aspose.words.settings/)
* hopsättning [Aspose.Words](../../)


