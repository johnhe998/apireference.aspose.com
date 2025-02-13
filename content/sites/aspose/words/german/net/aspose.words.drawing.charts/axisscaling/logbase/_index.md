---
title: AxisScaling.LogBase
second_title: Aspose.Words für .NET-API-Referenz
description: AxisScaling eigendom. Ruft die logarithmische Basis für eine logarithmische Achse ab oder legt sie fest.
type: docs
weight: 20
url: /de/net/aspose.words.drawing.charts/axisscaling/logbase/
---
## AxisScaling.LogBase property

Ruft die logarithmische Basis für eine logarithmische Achse ab oder legt sie fest.

```csharp
public double LogBase { get; set; }
```

### Bemerkungen

Die Eigenschaft wird von MS Office 2016 New Charts nicht unterstützt.

Der gültige Bereich eines Gleitkommawerts ist größer oder gleich 2 und kleiner oder gleich 1000. Die Eigenschaft hat nur dann eine Auswirkung, wenn[`Type`](../type/) ist auf eingestelltLogarithmic.

Durch Festlegen dieser Eigenschaft wird die[`Type`](../type/) Eigentum zuLogarithmic .

### Beispiele

Zeigt, wie eine logarithmische Skalierung auf eine Diagrammachse angewendet wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape chartShape = builder.InsertChart(ChartType.Scatter, 450, 300);
Chart chart = chartShape.Chart;

// Löschen Sie die Demo-Datenreihe des Diagramms, um mit einem sauberen Diagramm zu beginnen.
chart.Series.Clear();

// Eine Serie mit X/Y-Koordinaten für fünf Punkte einfügen.
chart.Series.Add("Series 1", 
    new[] { 1.0, 2.0, 3.0, 4.0, 5.0 }, 
    new[] { 1.0, 20.0, 400.0, 8000.0, 160000.0 });

// Die Skalierung der X-Achse ist standardmäßig linear,
// Anzeigen von gleichmäßig steigenden Werten, die unseren X-Wertebereich abdecken (0, 1, 2, 3 ...).
// Eine Linearachse ist für unsere Y-Werte nicht ideal
// da die Punkte mit den kleineren Y-Werten schwerer zu lesen sind.
// Eine logarithmische Skalierung mit einer Basis von 20 (1, 20, 400, 8000...)
// verteilt die gezeichneten Punkte, sodass wir ihre Werte auf dem Diagramm leichter ablesen können.
chart.AxisY.Scaling.Type = AxisScaleType.Logarithmic;
chart.AxisY.Scaling.LogBase = 20;

doc.Save(ArtifactsDir + "Charts.AxisScaling.docx");
```

### Siehe auch

* class [AxisScaling](../)
* namensraum [Aspose.Words.Drawing.Charts](../../axisscaling/)
* Montage [Aspose.Words](../../../)


