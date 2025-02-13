---
title: ChartAxis.NumberFormat
second_title: Aspose.Words für .NET-API-Referenz
description: ChartAxis eigendom. Gibt a zurückChartNumberFormat Objekt mit dem Zahlenformate für die Achse definiert werden können.
type: docs
weight: 170
url: /de/net/aspose.words.drawing.charts/chartaxis/numberformat/
---
## ChartAxis.NumberFormat property

Gibt a zurück[`ChartNumberFormat`](../../chartnumberformat/) Objekt, mit dem Zahlenformate für die Achse definiert werden können.

```csharp
public ChartNumberFormat NumberFormat { get; }
```

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

* class [ChartNumberFormat](../../chartnumberformat/)
* class [ChartAxis](../)
* namensraum [Aspose.Words.Drawing.Charts](../../chartaxis/)
* Montage [Aspose.Words](../../../)


