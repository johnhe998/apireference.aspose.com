---
title: Chart.SourceFullName
second_title: Référence de l'API Aspose.Words pour .NET
description: Chart propriété. Obtient le chemin et le nom dun fichier xls/xlsx auquel ce graphique est lié.
type: docs
weight: 60
url: /fr/net/aspose.words.drawing.charts/chart/sourcefullname/
---
## Chart.SourceFullName property

Obtient le chemin et le nom d'un fichier xls/xlsx auquel ce graphique est lié.

```csharp
public string SourceFullName { get; set; }
```

### Exemples

Montre comment obtenir le nom complet du document xls/xlsx externe si le graphique est lié.

```csharp
Document doc = new Document(MyDir + "Shape with linked chart.docx");

Shape shape = (Shape)doc.GetChild(NodeType.Shape, 0, true);

Assert.True(shape.Chart.SourceFullName.Contains("Examples\\Data\\Spreadsheet.xlsx"));
```

### Voir également

* class [Chart](../)
* espace de noms [Aspose.Words.Drawing.Charts](../../chart/)
* Assemblée [Aspose.Words](../../../)


