---
title: ChartNumberFormat.IsLinkedToSource
second_title: Aspose.Words für .NET-API-Referenz
description: ChartNumberFormat eigendom. Gibt an ob der Formatcode mit einer Quellzelle verknüpft ist. Standard ist wahr.
type: docs
weight: 20
url: /de/net/aspose.words.drawing.charts/chartnumberformat/islinkedtosource/
---
## ChartNumberFormat.IsLinkedToSource property

Gibt an, ob der Formatcode mit einer Quellzelle verknüpft ist. Standard ist wahr.

```csharp
public bool IsLinkedToSource { get; set; }
```

### Bemerkungen

Das NumberFormat wird auf allgemein zurückgesetzt, wenn der Formatcode mit der Quelle verknüpft ist.

### Beispiele

Zeigt, wie Sie die Formatierung für Diagrammwerte festlegen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertChart(ChartType.Column, 500, 300);
Chart chart = shape.Chart;

// Löschen Sie die Demo-Datenreihe des Diagramms, um mit einem sauberen Diagramm zu beginnen.
chart.Series.Clear();

// Hinzufügen einer benutzerdefinierten Reihe zum Diagramm mit Kategorien für die X-Achse,
 // und große entsprechende numerische Werte für die Y-Achse.
chart.Series.Add("Aspose Test Series",
    new [] { "Word", "PDF", "Excel", "GoogleDocs", "Note" },
    new double[] { 1900000, 850000, 2100000, 600000, 1500000 });

 // Stellen Sie das Zahlenformat der Tick-Beschriftungen der Y-Achse so ein, dass Ziffern nicht mit Kommas gruppiert werden.
chart.AxisY.NumberFormat.FormatCode = "#,##0";

// Dieses Flag kann den obigen Wert überschreiben und das Zahlenformat aus der Quellzelle ziehen.
Assert.False(chart.AxisY.NumberFormat.IsLinkedToSource);

doc.Save(ArtifactsDir + "Charts.SetNumberFormatToChartAxis.docx");
```

### Siehe auch

* class [ChartNumberFormat](../)
* namensraum [Aspose.Words.Drawing.Charts](../../chartnumberformat/)
* Montage [Aspose.Words](../../../)


