---
title: CalculateFormulas
second_title: Référence de l'API Aspose.Slides pour .NET
description: Calcule toutes les formules du classeur et met à jour les valeurs des cellules correspondantes.
type: docs
weight: 20
url: /fr/net/aspose.slides.charts/ichartdataworkbook/calculateformulas/
---
## IChartDataWorkbook.CalculateFormulas method

Calcule toutes les formules du classeur et met à jour les valeurs des cellules correspondantes.

```csharp
public void CalculateFormulas()
```

### Exceptions

| exception | condition |
| --- | --- |
| [CellCircularReferenceException](../../../aspose.slides.spreadsheet/cellcircularreferenceexception) | Le classeur contient des formules avec une référence circulaire. |
| [CellUnsupportedDataException](../../../aspose.slides.spreadsheet/cellunsupporteddataexception) | Les données de cellule ne sont pas prises en charge. |

### Exemples

L'exemple montre comment affecter une formule à la cellule et calculer une valeur. La valeur de la cellule "B4" est définie sur 5.

```csharp
[C#]
using (Presentation pres = new Presentation())
{
    IChart chart = pres.Slides[0].Shapes.AddChart(ChartType.Pie, 100, 100, 300, 400);
    IChartDataWorkbook wb = chart.ChartData.ChartDataWorkbook;
    wb.GetCell(0, "B2", 2);	
	wb.GetCell(0, "B3", 3);	
    wb.GetCell(0, "B4").Formula = "B2+B3";
    wb.CalculateFormulas();
    ...
}
```

### Voir également

* interface [IChartDataWorkbook](../../ichartdataworkbook)
* espace de noms [Aspose.Slides.Charts](../../ichartdataworkbook)
* Assemblée [Aspose.Slides](../../../)

<!-- DO NOT EDIT: generated by xmldocmd for Aspose.Slides.dll -->
