---
title: ChartAxis.Hidden
second_title: Référence de l'API Aspose.Words pour .NET
description: ChartAxis propriété. Obtient ou définit un indicateur indiquant si cet axe est masqué ou non.
type: docs
weight: 80
url: /fr/net/aspose.words.drawing.charts/chartaxis/hidden/
---
## ChartAxis.Hidden property

Obtient ou définit un indicateur indiquant si cet axe est masqué ou non.

```csharp
public bool Hidden { get; set; }
```

### Remarques

La valeur par défaut est **faux** .

### Exemples

Montre comment masquer les axes du graphique.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertChart(ChartType.Line, 500, 300);
Chart chart = shape.Chart;

// Effacez la série de données de démonstration du graphique pour commencer avec un graphique propre.
chart.Series.Clear();

// Ajoutez une série personnalisée avec des catégories pour l'axe X et des valeurs décimales respectives pour l'axe Y.
chart.Series.Add("AW Series 1",
    new[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new[] { 1.2, 0.3, 2.1, 2.9, 4.2 });

 // Masque les axes du graphique pour simplifier l'apparence du graphique.
chart.AxisX.Hidden = true;
chart.AxisY.Hidden = true;

doc.Save(ArtifactsDir + "Charts.HideChartAxis.docx");
```

### Voir également

* class [ChartAxis](../)
* espace de noms [Aspose.Words.Drawing.Charts](../../chartaxis/)
* Assemblée [Aspose.Words](../../../)


