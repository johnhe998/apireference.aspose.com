---
title: ChartDataLabelCollection.ShowLegendKey
second_title: Aspose.Words för .NET API Referens
description: ChartDataLabelCollection fast egendom. Gör det möjligt att ange om förklaringsnyckeln ska visas för dataetiketterna för hela serien. Standardvärdet är falsk .
type: docs
weight: 90
url: /sv/net/aspose.words.drawing.charts/chartdatalabelcollection/showlegendkey/
---
## ChartDataLabelCollection.ShowLegendKey property

Gör det möjligt att ange om förklaringsnyckeln ska visas för dataetiketterna för hela serien. Standardvärdet är **falsk** .

```csharp
public bool ShowLegendKey { get; set; }
```

### Anmärkningar

Värdet som definierats för den här egenskapen kan åsidosättas för en individuell dataetikett med hjälp av [`ShowLegendKey`](../../chartdatalabel/showlegendkey/) egenskap.

### Exempel

Visar hur man arbetar med dataetiketter i ett cirkeldiagram.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Chart chart = builder.InsertChart(ChartType.Pie, 500, 300).Chart;

// Rensa diagrammets demodataserie för att börja med ett rent diagram.
chart.Series.Clear();

// Infoga en anpassad diagramserie med ett kategorinamn för var och en av sektorerna och deras frekvenstabell.
ChartSeries series = chart.Series.Add("Aspose Test Series",
    new[] { "Word", "PDF", "Excel" },
    new[] { 2.7, 3.2, 0.8 });

// Aktivera dataetiketter som visar både procent och frekvens för varje sektor, och ändra deras utseende.
series.HasDataLabels = true;
ChartDataLabelCollection dataLabels = series.DataLabels;
dataLabels.ShowLeaderLines = true;
dataLabels.ShowLegendKey = true;
dataLabels.ShowPercentage = true;
dataLabels.ShowValue = true;
dataLabels.Separator = "; ";

doc.Save(ArtifactsDir + "Charts.DataLabelsPieChart.docx");
```

### Se även

* class [ChartDataLabelCollection](../)
* namnutrymme [Aspose.Words.Drawing.Charts](../../chartdatalabelcollection/)
* hopsättning [Aspose.Words](../../../)


