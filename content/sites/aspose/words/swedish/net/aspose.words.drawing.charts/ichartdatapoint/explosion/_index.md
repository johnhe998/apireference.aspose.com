---
title: IChartDataPoint.Explosion
second_title: Aspose.Words för .NET API Referens
description: IChartDataPoint fast egendom. Anger hur mycket datapunkten ska flyttas från mitten av cirkeln. Kan vara negativ negativ betyder att egenskapen inte är inställd och ingen explosion ska tillämpas. Gäller endast cirkeldiagram.
type: docs
weight: 20
url: /sv/net/aspose.words.drawing.charts/ichartdatapoint/explosion/
---
## IChartDataPoint.Explosion property

Anger hur mycket datapunkten ska flyttas från mitten av cirkeln. Kan vara negativ, negativ betyder att egenskapen inte är inställd och ingen explosion ska tillämpas. Gäller endast cirkeldiagram.

```csharp
public int Explosion { get; set; }
```

### Exempel

Visar hur man flyttar skivorna i ett cirkeldiagram bort från mitten.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertChart(ChartType.Pie, 500, 350);
Chart chart = shape.Chart;

Assert.AreEqual(1, chart.Series.Count);
Assert.AreEqual("Sales", chart.Series[0].Name);

// "Slices" av ett cirkeldiagram kan flyttas bort från mitten ett avstånd via respektive datapunkts Explosion-attribut.
// Lägg till en datapunkt till den första delen av cirkeldiagrammet och flytta den bort från mitten med 10 punkter.
// Aspose.Words skapar datapunkter automatiskt om de inte finns.
ChartDataPoint dataPoint = chart.Series[0].DataPoints[0];
dataPoint.Explosion = 10;

// Förskjut den andra delen med ett större avstånd.
dataPoint = chart.Series[0].DataPoints[1];
dataPoint.Explosion = 40;

doc.Save(ArtifactsDir + "Charts.PieChartExplosion.docx");
```

### Se även

* interface [IChartDataPoint](../)
* namnutrymme [Aspose.Words.Drawing.Charts](../../ichartdatapoint/)
* hopsättning [Aspose.Words](../../../)


