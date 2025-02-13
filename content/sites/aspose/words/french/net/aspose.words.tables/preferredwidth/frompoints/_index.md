---
title: PreferredWidth.FromPoints
second_title: Référence de l'API Aspose.Words pour .NET
description: PreferredWidth méthode. Une méthode de création qui renvoie une nouvelle instance qui représente une largeur préférée spécifiée à laide dun nombre de points.
type: docs
weight: 30
url: /fr/net/aspose.words.tables/preferredwidth/frompoints/
---
## PreferredWidth.FromPoints method

Une méthode de création qui renvoie une nouvelle instance qui représente une largeur préférée spécifiée à l'aide d'un nombre de points.

```csharp
public static PreferredWidth FromPoints(double points)
```

| Paramètre | Taper | La description |
| --- | --- | --- |
| points | Double | La valeur doit être comprise entre 0 et 22 pouces (22 * 72 points). |

### Exemples

Montre comment utiliser les outils de conversion d'unité tout en spécifiant une largeur préférée pour une cellule.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(ConvertUtil.InchToPoint(3));
builder.InsertCell();

Assert.AreEqual(216.0d, table.FirstRow.FirstCell.CellFormat.PreferredWidth.Value);
```

Montre comment définir une largeur préférée pour les cellules de tableau.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.StartTable();

// Il existe deux manières d'appliquer la classe "PreferredWidth" aux cellules d'un tableau.
// 1 - Définissez une largeur préférée absolue basée sur les points :
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
builder.Writeln($"Cell with a width of {builder.CellFormat.PreferredWidth}.");

// 2 - Définissez une largeur préférée relative basée sur le pourcentage de la largeur du tableau :
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
builder.Writeln($"Cell with a width of {builder.CellFormat.PreferredWidth}.");

builder.InsertCell();

// Une cellule sans largeur préférée spécifiée occupera le reste de l'espace disponible.
builder.CellFormat.PreferredWidth = PreferredWidth.Auto;

// Chaque configuration de la propriété "PreferredWidth" crée un nouvel objet.
Assert.AreNotEqual(table.FirstRow.Cells[1].CellFormat.PreferredWidth.GetHashCode(),
    builder.CellFormat.PreferredWidth.GetHashCode());

builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
builder.Writeln("Automatically sized cell.");

doc.Save(ArtifactsDir + "DocumentBuilder.InsertCellsWithPreferredWidths.docx");
```

### Voir également

* class [PreferredWidth](../)
* espace de noms [Aspose.Words.Tables](../../preferredwidth/)
* Assemblée [Aspose.Words](../../../)


