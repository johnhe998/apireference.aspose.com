---
title: ChartAxis.AxisBetweenCategories
second_title: Aspose.Words för .NET API Referens
description: ChartAxis fast egendom. Hämtar eller sätter en flagga som indikerar om värdeaxeln korsar kategoriaxeln mellan kategorier.
type: docs
weight: 10
url: /sv/net/aspose.words.drawing.charts/chartaxis/axisbetweencategories/
---
## ChartAxis.AxisBetweenCategories property

Hämtar eller sätter en flagga som indikerar om värdeaxeln korsar kategoriaxeln mellan kategorier.

```csharp
public bool AxisBetweenCategories { get; set; }
```

### Anmärkningar

Egenskapen har effekt endast för värdeaxlar. Det stöds inte av MS Office 2016 nya diagram.

### Exempel

Visar hur man får en grafaxel att korsa på en anpassad plats.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertChart(ChartType.Column, 450, 250);
Chart chart = shape.Chart;

Assert.AreEqual(3, chart.Series.Count);
Assert.AreEqual("Series 1", chart.Series[0].Name);
Assert.AreEqual("Series 2", chart.Series[1].Name);
Assert.AreEqual("Series 3", chart.Series[2].Name);

// För kolumndiagram korsar Y-axeln vid noll som standard,
// vilket betyder att kolumner för alla värden under noll pekar ner för att representera negativa värden.
// Vi kan ställa in ett annat värde för Y-axelns korsning. I det här fallet kommer vi att ställa in den till 3.
ChartAxis axis = chart.AxisX;
axis.Crosses = AxisCrosses.Custom;
axis.CrossesAt = 3;
axis.AxisBetweenCategories = true;

doc.Save(ArtifactsDir + "Charts.AxisCross.docx");
```

### Se även

* class [ChartAxis](../)
* namnutrymme [Aspose.Words.Drawing.Charts](../../chartaxis/)
* hopsättning [Aspose.Words](../../../)


