---
title: TextColumn.SpaceAfter
second_title: Référence de l'API Aspose.Words pour .NET
description: TextColumn propriété. Obtient ou définit lespace entre cette colonne et la colonne suivante en points. Non requis pour la dernière colonne.
type: docs
weight: 10
url: /fr/net/aspose.words/textcolumn/spaceafter/
---
## TextColumn.SpaceAfter property

Obtient ou définit l'espace entre cette colonne et la colonne suivante en points. Non requis pour la dernière colonne.

```csharp
public double SpaceAfter { get; set; }
```

### Exemples

Montre comment créer des colonnes espacées de manière inégale.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
PageSetup pageSetup = builder.PageSetup;

TextColumnCollection columns = pageSetup.TextColumns;
columns.EvenlySpaced = false;
columns.SetCount(2);

// Déterminer la quantité d'espace dont nous disposons pour organiser les colonnes.
double contentWidth = pageSetup.PageWidth - pageSetup.LeftMargin - pageSetup.RightMargin;

Assert.AreEqual(470.30d, contentWidth, 0.01d);

// Définit la première colonne comme étant étroite.
TextColumn column = columns[0];
column.Width = 100;
column.SpaceAfter = 20;

// Définissez la deuxième colonne pour occuper le reste de l'espace disponible dans les marges de la page.
column = columns[1];
column.Width = contentWidth - column.Width - column.SpaceAfter;

builder.Writeln("Narrow column 1.");
builder.InsertBreak(BreakType.ColumnBreak);
builder.Writeln("Wide column 2.");

doc.Save(ArtifactsDir + "PageSetup.CustomColumnWidth.docx");
```

### Voir également

* class [TextColumn](../)
* espace de noms [Aspose.Words](../../textcolumn/)
* Assemblée [Aspose.Words](../../../)


