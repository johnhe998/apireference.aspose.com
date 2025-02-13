---
title: Enum AxisTickLabelPosition
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Drawing.Charts.AxisTickLabelPosition opsomming. Gibt die möglichen Positionen für Teilstrichbeschriftungen an.
type: docs
weight: 570
url: /de/net/aspose.words.drawing.charts/axisticklabelposition/
---
## AxisTickLabelPosition enumeration

Gibt die möglichen Positionen für Teilstrichbeschriftungen an.

```csharp
public enum AxisTickLabelPosition
```

### Werte

| Name | Wert | Beschreibung |
| --- | --- | --- |
| High | `0` | Gibt an, dass die Achsenbeschriftungen am oberen Ende der senkrechten Achse liegen sollen. |
| Low | `1` | Gibt an, dass sich die Achsenbeschriftungen am unteren Ende der senkrechten Achse befinden sollen. |
| NextToAxis | `2` | Gibt an, dass die Achsenbeschriftungen neben der Achse stehen sollen. |
| None | `3` | Gibt an, dass die Achsenbeschriftungen nicht gezeichnet werden. |
| Default | `2` | Gibt den Standardwert der Position der Teilstrichbeschriftungen an. |

### Beispiele

Zeigt, wie ein Diagramm mit Datums-/Uhrzeitwerten eingefügt wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertChart(ChartType.Line, 500, 300);
Chart chart = shape.Chart;

// Löschen Sie die Demo-Datenreihe des Diagramms, um mit einem sauberen Diagramm zu beginnen.
chart.Series.Clear();

// Fügen Sie eine benutzerdefinierte Reihe hinzu, die Datums-/Uhrzeitwerte für die X-Achse und entsprechende Dezimalwerte für die Y-Achse enthält.
chart.Series.Add("Aspose Test Series",
    new[]
    {
        new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
        new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
    },
    new[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });

// Untere und obere Grenzen für die X-Achse setzen.
ChartAxis xAxis = chart.AxisX;
xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03));

// Setze die Haupteinheiten der X-Achse auf eine Woche und die Nebeneinheiten auf einen Tag.
xAxis.BaseTimeUnit = AxisTimeUnit.Days;
xAxis.MajorUnit = 7.0d;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorUnit = 1.0d;
xAxis.MinorTickMark = AxisTickMark.Outside;

// Eigenschaften der Y-Achse für Dezimalwerte definieren.
ChartAxis yAxis = chart.AxisY;
yAxis.TickLabelPosition = AxisTickLabelPosition.High;
yAxis.MajorUnit = 100.0d;
yAxis.MinorUnit = 50.0d;
yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
yAxis.Scaling.Minimum = new AxisBound(100);
yAxis.Scaling.Maximum = new AxisBound(700);

doc.Save(ArtifactsDir + "Charts.DateTimeValues.docx");
```

### Siehe auch

* namensraum [Aspose.Words.Drawing.Charts](../../aspose.words.drawing.charts/)
* Montage [Aspose.Words](../../)


