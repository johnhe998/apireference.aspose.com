---
title: ChartNumberFormat.IsLinkedToSource
second_title: Référence de l'API Aspose.Words pour .NET
description: ChartNumberFormat propriété. Spécifie si le code de format est lié à une cellule source. La valeur par défaut est true.
type: docs
weight: 20
url: /fr/net/aspose.words.drawing.charts/chartnumberformat/islinkedtosource/
---
## ChartNumberFormat.IsLinkedToSource property

Spécifie si le code de format est lié à une cellule source. La valeur par défaut est true.

```csharp
public bool IsLinkedToSource { get; set; }
```

### Remarques

Le NumberFormat sera réinitialisé à général si le code de format est lié à la source.

### Exemples

Montre comment définir la mise en forme des valeurs de graphique.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertChart(ChartType.Column, 500, 300);
Chart chart = shape.Chart;

// Effacez la série de données de démonstration du graphique pour commencer avec un graphique propre.
chart.Series.Clear();

// Ajoute une série personnalisée au graphique avec des catégories pour l'axe X,
 // et de grandes valeurs numériques respectives pour l'axe Y.
chart.Series.Add("Aspose Test Series",
    new [] { "Word", "PDF", "Excel", "GoogleDocs", "Note" },
    new double[] { 1900000, 850000, 2100000, 600000, 1500000 });

 // Définissez le format numérique des étiquettes de graduation de l'axe Y pour ne pas grouper les chiffres avec des virgules.
chart.AxisY.NumberFormat.FormatCode = "#,##0";

// Cet indicateur peut remplacer la valeur ci-dessus et tirer le format numérique de la cellule source.
Assert.False(chart.AxisY.NumberFormat.IsLinkedToSource);

doc.Save(ArtifactsDir + "Charts.SetNumberFormatToChartAxis.docx");
```

### Voir également

* class [ChartNumberFormat](../)
* espace de noms [Aspose.Words.Drawing.Charts](../../chartnumberformat/)
* Assemblée [Aspose.Words](../../../)


