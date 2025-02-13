---
title: Document.ExpandTableStylesToDirectFormatting
second_title: Aspose.Words för .NET API Referens
description: Document metod. Konverterar formatering som anges i tabellstilar till direkt formatering på tabeller i dokumentet.
type: docs
weight: 570
url: /sv/net/aspose.words/document/expandtablestylestodirectformatting/
---
## Document.ExpandTableStylesToDirectFormatting method

Konverterar formatering som anges i tabellstilar till direkt formatering på tabeller i dokumentet.

```csharp
public void ExpandTableStylesToDirectFormatting()
```

### Anmärkningar

Denna metod existerar eftersom den här versionen av Aspose.Words endast ger begränsat stöd för tabellstilar (se nedan). Den här metoden kan vara användbar när du laddar ett DOCX- eller WordprocessingML -dokument som innehåller tabeller formaterade med tabellstilar och du behöver fråga formatering av tabeller, celler, stycken eller text.

Den här versionen av Aspose.Words ger begränsat stöd för tabellstilar enligt följande:

* Tabellstilar som definieras i DOCX- eller WordprocessingML-dokument bevaras som tabellstilar när dokumentet sparas som DOCX eller WordprocessingML.
* Tabellstilar som definieras i DOCX- eller WordprocessingML-dokument konverteras automatiskt till direktformatering på tabeller när dokumentet sparas i något annat format, rendering eller utskrift.
* Tabellstilar som definieras i DOC-dokument bevaras som tabellstilar när endast sparar dokumentet som DOC.

### Exempel

Visar hur man tillämpar egenskaperna för en tabells stil direkt på tabellens element.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Hello world!");
builder.EndTable();

TableStyle tableStyle = (TableStyle)doc.Styles.Add(StyleType.Table, "MyTableStyle1");
tableStyle.RowStripe = 3;
tableStyle.CellSpacing = 5;
tableStyle.Shading.BackgroundPatternColor = Color.AntiqueWhite;
tableStyle.Borders.Color = Color.Blue;
tableStyle.Borders.LineStyle = LineStyle.DotDash;

table.Style = tableStyle;

// Den här metoden gäller tabellstilsegenskaper som de vi ställt in ovan.
doc.ExpandTableStylesToDirectFormatting();

doc.Save(ArtifactsDir + "Document.TableStyleToDirectFormatting.docx");
```

### Se även

* class [Document](../)
* namnutrymme [Aspose.Words](../../document/)
* hopsättning [Aspose.Words](../../../)


