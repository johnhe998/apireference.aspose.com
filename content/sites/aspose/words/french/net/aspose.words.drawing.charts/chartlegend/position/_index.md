---
title: ChartLegend.Position
second_title: Référence de l'API Aspose.Words pour .NET
description: ChartLegend propriété. Spécifie la position de la légende sur un graphique. La valeur par défaut estRight .
type: docs
weight: 30
url: /fr/net/aspose.words.drawing.charts/chartlegend/position/
---
## ChartLegend.Position property

Spécifie la position de la légende sur un graphique. La valeur par défaut estRight .

```csharp
public LegendPosition Position { get; set; }
```

### Exemples

Montre comment modifier l'apparence de la légende d'un graphique.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertChart(ChartType.Line, 450, 300);
Chart chart = shape.Chart;

Assert.AreEqual(3, chart.Series.Count);
Assert.AreEqual("Series 1", chart.Series[0].Name);
Assert.AreEqual("Series 2", chart.Series[1].Name);
Assert.AreEqual("Series 3", chart.Series[2].Name);

// Déplace la légende du graphique dans le coin supérieur droit.
ChartLegend legend = chart.Legend;
legend.Position = LegendPosition.TopRight;

// Donnez aux autres éléments du graphique, tels que le graphique, plus d'espace en leur permettant de chevaucher la légende.
legend.Overlay = true;

doc.Save(ArtifactsDir + "Charts.ChartLegend.docx");
```

### Voir également

* enum [LegendPosition](../../legendposition/)
* class [ChartLegend](../)
* espace de noms [Aspose.Words.Drawing.Charts](../../chartlegend/)
* Assemblée [Aspose.Words](../../../)


