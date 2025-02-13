---
title: Class ChartLegend
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.Drawing.Charts.ChartLegend klass. Representerar diagramförklaringsegenskaper.
type: docs
weight: 680
url: /sv/net/aspose.words.drawing.charts/chartlegend/
---
## ChartLegend class

Representerar diagramförklaringsegenskaper.

```csharp
public class ChartLegend
```

## Egenskaper

| namn | Beskrivning |
| --- | --- |
| [LegendEntries](../../aspose.words.drawing.charts/chartlegend/legendentries/) { get; } | Returnerar en samling förklaringsposter för alla serier och trendlinjer i det överordnade diagrammet. |
| [Overlay](../../aspose.words.drawing.charts/chartlegend/overlay/) { get; set; } | Bestämmer om andra diagramelement ska tillåtas att överlappa förklaringen. Standardvärdet är falskt. |
| [Position](../../aspose.words.drawing.charts/chartlegend/position/) { get; set; } | Anger positionen för förklaringen på ett diagram. Standardvärdet ärRight . |

### Exempel

Visar hur man redigerar utseendet på ett diagrams förklaring.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertChart(ChartType.Line, 450, 300);
Chart chart = shape.Chart;

Assert.AreEqual(3, chart.Series.Count);
Assert.AreEqual("Series 1", chart.Series[0].Name);
Assert.AreEqual("Series 2", chart.Series[1].Name);
Assert.AreEqual("Series 3", chart.Series[2].Name);

// Flytta diagrammets förklaring till det övre högra hörnet.
ChartLegend legend = chart.Legend;
legend.Position = LegendPosition.TopRight;

// Ge andra diagramelement, som grafen, mer utrymme genom att låta dem överlappa förklaringen.
legend.Overlay = true;

doc.Save(ArtifactsDir + "Charts.ChartLegend.docx");
```

### Se även

* namnutrymme [Aspose.Words.Drawing.Charts](../../aspose.words.drawing.charts/)
* hopsättning [Aspose.Words](../../)


