---
title: Class ChartNumberFormat
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Drawing.Charts.ChartNumberFormat klas. Stellt die Zahlenformatierung des übergeordneten Elements dar.
type: docs
weight: 720
url: /de/net/aspose.words.drawing.charts/chartnumberformat/
---
## ChartNumberFormat class

Stellt die Zahlenformatierung des übergeordneten Elements dar.

```csharp
public class ChartNumberFormat
```

## Eigenschaften

| Name | Beschreibung |
| --- | --- |
| [FormatCode](../../aspose.words.drawing.charts/chartnumberformat/formatcode/) { get; set; } | Ruft den auf eine Datenbeschriftung angewendeten Formatcode ab oder legt ihn fest. |
| [IsLinkedToSource](../../aspose.words.drawing.charts/chartnumberformat/islinkedtosource/) { get; set; } | Gibt an, ob der Formatcode mit einer Quellzelle verknüpft ist. Standard ist wahr. |

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

* namensraum [Aspose.Words.Drawing.Charts](../../aspose.words.drawing.charts/)
* Montage [Aspose.Words](../../)


