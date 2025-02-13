---
title: Class ImportFormatOptions
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.ImportFormatOptions klass. Gör det möjligt att ange olika importalternativ för att formatera utdata.
type: docs
weight: 3040
url: /sv/net/aspose.words/importformatoptions/
---
## ImportFormatOptions class

Gör det möjligt att ange olika importalternativ för att formatera utdata.

```csharp
public class ImportFormatOptions
```

## Konstruktörer

| namn | Beskrivning |
| --- | --- |
| [ImportFormatOptions](importformatoptions/)() | Default_Constructor |

## Egenskaper

| namn | Beskrivning |
| --- | --- |
| [ForceCopyStyles](../../aspose.words/importformatoptions/forcecopystyles/) { get; set; } | Hämtar eller ställer in ett booleskt värde som anger antingen att kopiera motstridiga stilar inKeepSourceFormatting mode. Standardvärdet är`falsk` . |
| [IgnoreHeaderFooter](../../aspose.words/importformatoptions/ignoreheaderfooter/) { get; set; } | Hämtar eller ställer in ett booleskt värde som anger att källformateringen av sidhuvuden/sidfotsinnehåll ignoreras omKeepSourceFormatting läge används. Standardvärdet är`Sann` . |
| [IgnoreTextBoxes](../../aspose.words/importformatoptions/ignoretextboxes/) { get; set; } | Hämtar eller ställer in ett booleskt värde som anger att källformatering av textrutor innehåll ignored omKeepSourceFormatting läge används. Standardvärdet är`Sann` . |
| [KeepSourceNumbering](../../aspose.words/importformatoptions/keepsourcenumbering/) { get; set; } | Hämtar eller ställer in ett booleskt värde som anger hur numreringen kommer att importeras när den krockar i käll- och destinationsdokument. Standardvärdet är`falsk` . |
| [MergePastedLists](../../aspose.words/importformatoptions/mergepastedlists/) { get; set; } | Hämtar eller ställer in ett booleskt värde som anger om inklistrade listor ska slås samman med omgivande listor. Standardvärdet är`falsk` . |
| [SmartStyleBehavior](../../aspose.words/importformatoptions/smartstylebehavior/) { get; set; } | Hämtar eller ställer in ett booleskt värde som anger hur stilar kommer att importeras när de har samma namn i käll- och måldokument. Standardvärdet är`falsk` . |

### Exempel

Visar hur du löser dubbletter av stilar när du infogar dokument.

```csharp
Document dstDoc = new Document();
DocumentBuilder builder = new DocumentBuilder(dstDoc);

Style myStyle = builder.Document.Styles.Add(StyleType.Paragraph, "MyStyle");
myStyle.Font.Size = 14;
myStyle.Font.Name = "Courier New";
myStyle.Font.Color = Color.Blue;

builder.ParagraphFormat.StyleName = myStyle.Name;
builder.Writeln("Hello world!");

// Klona dokumentet och redigera klonens "MyStyle"-stil, så det är en annan färg än originalets.
// Om vi infogar klonen i originaldokumentet kommer de två stilarna med samma namn att orsaka en konflikt.
Document srcDoc = dstDoc.Clone();
srcDoc.Styles["MyStyle"].Font.Color = Color.Red;

// När vi aktiverar SmartStyleBehavior och använder importformatläget KeepSourceFormatting,
// Aspose.Words kommer att lösa stilkrockar genom att konvertera källdokumentstilar.
// med samma namn som målstilar till direkta styckeattribut.
ImportFormatOptions options = new ImportFormatOptions();
options.SmartStyleBehavior = true;

builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting, options);

dstDoc.Save(ArtifactsDir + "DocumentBuilder.SmartStyleBehavior.docx");
```

### Se även

* namnutrymme [Aspose.Words](../../aspose.words/)
* hopsättning [Aspose.Words](../../)


