---
title: ChartAxis.TickMarkSpacing
second_title: Aspose.Words für .NET-API-Referenz
description: ChartAxis eigendom. Holt oder setzt das Intervall in dem Teilstriche gezeichnet werden.
type: docs
weight: 250
url: /de/net/aspose.words.drawing.charts/chartaxis/tickmarkspacing/
---
## ChartAxis.TickMarkSpacing property

Holt oder setzt das Intervall, in dem Teilstriche gezeichnet werden.

```csharp
public int TickMarkSpacing { get; set; }
```

### Bemerkungen

Die Eigenschaft wirkt sich auf Textkategorie- und Reihenachsen aus. Es wird von MS Office 2016 new charts nicht unterstützt.

Der gültige Bereich eines Werts ist größer oder gleich 1.

### Beispiele

Zeigt, wie Sie ein Diagramm einfügen und das Aussehen seiner Achsen ändern.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertChart(ChartType.Column, 500, 300);
Chart chart = shape.Chart;

// Löschen Sie die Demo-Datenreihe des Diagramms, um mit einem sauberen Diagramm zu beginnen.
chart.Series.Clear();

// Einfügen einer Diagrammreihe mit Kategorien für die X-Achse und entsprechenden numerischen Werten für die Y-Achse.
chart.Series.Add("Aspose Test Series",
    new[] { "Word", "PDF", "Excel", "GoogleDocs", "Note" },
    new double[] { 640, 320, 280, 120, 150 });

// Diagrammachsen haben verschiedene Optionen, die ihr Aussehen ändern können,
// wie ihre Richtung, Haupt-/Nebeneinheiten-Ticks und Teilstriche.
ChartAxis xAxis = chart.AxisX;
xAxis.CategoryType = AxisCategoryType.Category;
xAxis.Crosses = AxisCrosses.Minimum;
xAxis.ReverseOrder = false;
xAxis.MajorTickMark = AxisTickMark.Inside;
xAxis.MinorTickMark = AxisTickMark.Cross;
xAxis.MajorUnit = 10.0d;
xAxis.MinorUnit = 15.0d;
xAxis.TickLabelOffset = 50;
xAxis.TickLabelPosition = AxisTickLabelPosition.Low;
xAxis.TickLabelSpacingIsAuto = false;
xAxis.TickMarkSpacing = 1;

ChartAxis yAxis = chart.AxisY;
yAxis.CategoryType = AxisCategoryType.Automatic;
yAxis.Crosses = AxisCrosses.Maximum;
yAxis.ReverseOrder = true;
yAxis.MajorTickMark = AxisTickMark.Inside;
yAxis.MinorTickMark = AxisTickMark.Cross;
yAxis.MajorUnit = 100.0d;
yAxis.MinorUnit = 20.0d;
yAxis.TickLabelPosition = AxisTickLabelPosition.NextToAxis;

// Säulendiagramme haben keine Z-Achse.
Assert.Null(chart.AxisZ);

doc.Save(ArtifactsDir + "Charts.AxisProperties.docx");
```

### Siehe auch

* class [ChartAxis](../)
* namensraum [Aspose.Words.Drawing.Charts](../../chartaxis/)
* Montage [Aspose.Words](../../../)


