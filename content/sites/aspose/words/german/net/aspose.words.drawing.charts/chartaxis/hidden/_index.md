---
title: ChartAxis.Hidden
second_title: Aspose.Words für .NET-API-Referenz
description: ChartAxis eigendom. Ruft oder setzt ein Flag das angibt ob diese Achse ausgeblendet ist oder nicht.
type: docs
weight: 80
url: /de/net/aspose.words.drawing.charts/chartaxis/hidden/
---
## ChartAxis.Hidden property

Ruft oder setzt ein Flag, das angibt, ob diese Achse ausgeblendet ist oder nicht.

```csharp
public bool Hidden { get; set; }
```

### Bemerkungen

Standardwert ist **FALSCH** .

### Beispiele

Zeigt, wie Diagrammachsen ausgeblendet werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertChart(ChartType.Line, 500, 300);
Chart chart = shape.Chart;

// Löschen Sie die Demo-Datenreihe des Diagramms, um mit einem sauberen Diagramm zu beginnen.
chart.Series.Clear();

// Fügen Sie eine benutzerdefinierte Reihe mit Kategorien für die X-Achse und entsprechenden Dezimalwerten für die Y-Achse hinzu.
chart.Series.Add("AW Series 1",
    new[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new[] { 1.2, 0.3, 2.1, 2.9, 4.2 });

 // Blenden Sie die Diagrammachsen aus, um das Erscheinungsbild des Diagramms zu vereinfachen.
chart.AxisX.Hidden = true;
chart.AxisY.Hidden = true;

doc.Save(ArtifactsDir + "Charts.HideChartAxis.docx");
```

### Siehe auch

* class [ChartAxis](../)
* namensraum [Aspose.Words.Drawing.Charts](../../chartaxis/)
* Montage [Aspose.Words](../../../)


