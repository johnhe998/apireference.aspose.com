---
title: ChartAxis.BaseTimeUnit
second_title: Aspose.Words för .NET API Referens
description: ChartAxis fast egendom. Returnerar eller ställer in den minsta tidsenheten som är representerad på tidskategoriaxeln.
type: docs
weight: 20
url: /sv/net/aspose.words.drawing.charts/chartaxis/basetimeunit/
---
## ChartAxis.BaseTimeUnit property

Returnerar eller ställer in den minsta tidsenheten som är representerad på tidskategoriaxeln.

```csharp
public AxisTimeUnit BaseTimeUnit { get; set; }
```

### Anmärkningar

Egenskapen har endast effekt för tidskategoriaxlar.

### Exempel

Visar hur man infogar diagram med datum/tidsvärden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertChart(ChartType.Line, 500, 300);
Chart chart = shape.Chart;

// Rensa diagrammets demodataserie för att börja med ett rent diagram.
chart.Series.Clear();

// Lägg till en anpassad serie som innehåller datum/tid-värden för X-axeln och respektive decimalvärden för Y-axeln.
chart.Series.Add("Aspose Test Series",
    new[]
    {
        new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
        new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
    },
    new[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });

// Sätt nedre och övre gränser för X-axeln.
ChartAxis xAxis = chart.AxisX;
xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03));

// Ställ in X-axelns huvudenheter till en vecka och de mindre enheterna till en dag.
xAxis.BaseTimeUnit = AxisTimeUnit.Days;
xAxis.MajorUnit = 7.0d;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorUnit = 1.0d;
xAxis.MinorTickMark = AxisTickMark.Outside;

// Definiera Y-axelegenskaper för decimalvärden.
ChartAxis yAxis = chart.AxisY;
yAxis.TickLabelPosition = AxisTickLabelPosition.High;
yAxis.MajorUnit = 100.0d;
yAxis.MinorUnit = 50.0d;
yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
yAxis.Scaling.Minimum = new AxisBound(100);
yAxis.Scaling.Maximum = new AxisBound(700);

doc.Save(ArtifactsDir + "Charts.DateTimeValues.docx");
```

### Se även

* enum [AxisTimeUnit](../../axistimeunit/)
* class [ChartAxis](../)
* namnutrymme [Aspose.Words.Drawing.Charts](../../chartaxis/)
* hopsättning [Aspose.Words](../../../)


