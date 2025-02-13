---
title: ChartDataLabelCollection.ShowCategoryName
second_title: Aspose.Words für .NET-API-Referenz
description: ChartDataLabelCollection eigendom. Ermöglicht die Angabe ob der Kategoriename für die Datenetiketten der gesamten Serie angezeigt werden soll. Standardwert ist FALSCH .
type: docs
weight: 60
url: /de/net/aspose.words.drawing.charts/chartdatalabelcollection/showcategoryname/
---
## ChartDataLabelCollection.ShowCategoryName property

Ermöglicht die Angabe, ob der Kategoriename für die Datenetiketten der gesamten Serie angezeigt werden soll. Standardwert ist **FALSCH** .

```csharp
public bool ShowCategoryName { get; set; }
```

### Bemerkungen

Der für diese Eigenschaft definierte Wert kann für eine einzelne Datenbeschriftung mit der Verwendung von überschrieben werden.[`ShowCategoryName`](../../chartdatalabel/showcategoryname/) Eigentum.

### Beispiele

Zeigt, wie mit Datenbeschriftungen eines Blasendiagramms gearbeitet wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Chart chart = builder.InsertChart(ChartType.Bubble, 500, 300).Chart;

// Löschen Sie die Demo-Datenreihe des Diagramms, um mit einem sauberen Diagramm zu beginnen.
chart.Series.Clear();

 // Fügen Sie eine benutzerdefinierte Serie mit X/Y-Koordinaten und Durchmesser jeder Blase hinzu.
ChartSeries series = chart.Series.Add("Aspose Test Series",
    new[] { 2.9, 3.5, 1.1, 4.0, 4.0 },
    new[] { 1.9, 8.5, 2.1, 6.0, 1.5 },
    new[] { 9.0, 4.5, 2.5, 8.0, 5.0 });

// Datenbeschriftungen aktivieren und dann deren Aussehen ändern.
series.HasDataLabels = true;
ChartDataLabelCollection dataLabels = series.DataLabels;
dataLabels.ShowBubbleSize = true;
dataLabels.ShowCategoryName = true;
dataLabels.ShowSeriesName = true;
dataLabels.Separator = " & ";

doc.Save(ArtifactsDir + "Charts.DataLabelsBubbleChart.docx");
```

### Siehe auch

* class [ChartDataLabelCollection](../)
* namensraum [Aspose.Words.Drawing.Charts](../../chartdatalabelcollection/)
* Montage [Aspose.Words](../../../)


