---
title: Class Chart
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.Drawing.Charts.Chart klass. Ger tillgång till diagramformens egenskaper.
type: docs
weight: 600
url: /sv/net/aspose.words.drawing.charts/chart/
---
## Chart class

Ger tillgång till diagramformens egenskaper.

```csharp
public class Chart
```

## Egenskaper

| namn | Beskrivning |
| --- | --- |
| [AxisX](../../aspose.words.drawing.charts/chart/axisx/) { get; } | Ger tillgång till egenskaperna för X-axeln i diagrammet. |
| [AxisY](../../aspose.words.drawing.charts/chart/axisy/) { get; } | Ger tillgång till egenskaperna för Y-axeln i diagrammet. |
| [AxisZ](../../aspose.words.drawing.charts/chart/axisz/) { get; } | Ger tillgång till egenskaperna för Z-axeln i diagrammet. |
| [Legend](../../aspose.words.drawing.charts/chart/legend/) { get; } | Ger tillgång till diagramförklaringsegenskaperna. |
| [Series](../../aspose.words.drawing.charts/chart/series/) { get; } | Ger tillgång till seriesamling. |
| [SourceFullName](../../aspose.words.drawing.charts/chart/sourcefullname/) { get; set; } | Hämtar sökvägen och namnet på en xls/xlsx-fil som detta diagram är länkat till. |
| [Title](../../aspose.words.drawing.charts/chart/title/) { get; } | Ger tillgång till egenskaperna för diagramtiteln. |

### Exempel

Visar hur man infogar ett diagram och ställer in en titel.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Infoga en diagramform med en dokumentbyggare och få dess diagram.
Shape chartShape = builder.InsertChart(ChartType.Bar, 400, 300);
Chart chart = chartShape.Chart;

// Använd egenskapen "Titel" för att ge vårt diagram en titel, som visas högst upp i mitten av diagramområdet.
ChartTitle title = chart.Title;
title.Text = "My Chart";

  // Ställ in egenskapen "Show" till "true" för att göra titeln synlig.
title.Show = true;

// Ställ in egenskapen "Overlay" på "true" Ge andra diagramelement mer utrymme genom att tillåta dem att överlappa titeln
title.Overlay = true;

doc.Save(ArtifactsDir + "Charts.ChartTitle.docx");
```

### Se även

* namnutrymme [Aspose.Words.Drawing.Charts](../../aspose.words.drawing.charts/)
* hopsättning [Aspose.Words](../../)


