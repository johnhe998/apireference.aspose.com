---
title: ChartSeries.Format
second_title: Référence de l'API Aspose.Words pour .NET
description: ChartSeries propriété. Fournit un accès au remplissage et à la mise en forme des lignes de la série.
type: docs
weight: 50
url: /fr/net/aspose.words.drawing.charts/chartseries/format/
---
## ChartSeries.Format property

Fournit un accès au remplissage et à la mise en forme des lignes de la série.

```csharp
public ChartFormat Format { get; }
```

### Exemples

Explique comment définir la couleur de la série.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertChart(ChartType.Column, 432, 252);

Chart chart = shape.Chart;
ChartSeriesCollection seriesColl = chart.Series;

// Supprime la série générée par défaut.
seriesColl.Clear();

// Crée un tableau de noms de catégories.
string[] categories = new[] { "Category 1", "Category 2" };

// Ajout d'une nouvelle série. Les tableaux de valeurs et de catégories doivent avoir la même taille.
ChartSeries series1 = seriesColl.Add("Series 1", categories, new double[] { 1, 2 });
ChartSeries series2 = seriesColl.Add("Series 2", categories, new double[] { 3, 4 });
ChartSeries series3 = seriesColl.Add("Series 3", categories, new double[] { 5, 6 });

// Définit la couleur de la série.
series1.Format.Fill.ForeColor = Color.Red;
series2.Format.Fill.ForeColor = Color.Yellow;
series3.Format.Fill.ForeColor = Color.Blue;

doc.Save(ArtifactsDir + "Charts.SeriesColor.docx");
```

### Voir également

* class [ChartFormat](../../chartformat/)
* class [ChartSeries](../)
* espace de noms [Aspose.Words.Drawing.Charts](../../chartseries/)
* Assemblée [Aspose.Words](../../../)


