---
title: Row.RowFormat
second_title: Référence de l'API Aspose.Words pour .NET
description: Row propriété. Permet daccéder aux propriétés de formatage de la ligne.
type: docs
weight: 90
url: /fr/net/aspose.words.tables/row/rowformat/
---
## Row.RowFormat property

Permet d'accéder aux propriétés de formatage de la ligne.

```csharp
public RowFormat RowFormat { get; }
```

### Exemples

Montre comment modifier la mise en forme d'une ligne de tableau.

```csharp
Document doc = new Document(MyDir + "Tables.docx");
Table table = doc.FirstSection.Body.Tables[0];

// Utilisez la propriété "RowFormat" de la première ligne pour définir le formatage qui modifie l'apparence de cette ligne entière.
Row firstRow = table.FirstRow;
firstRow.RowFormat.Borders.LineStyle = LineStyle.None;
firstRow.RowFormat.HeightRule = HeightRule.Auto;
firstRow.RowFormat.AllowBreakAcrossPages = true;

doc.Save(ArtifactsDir + "Table.RowFormat.docx");
```

Montre comment modifier le format des lignes et des cellules d'un tableau.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
builder.Write("City");
builder.InsertCell();
builder.Write("Country");
builder.EndRow();
builder.InsertCell();
builder.Write("London");
builder.InsertCell();
builder.Write("U.K.");
builder.EndTable();

// Utiliser la propriété "RowFormat" de la première ligne pour modifier la mise en forme
// du contenu de toutes les cellules de cette ligne.
RowFormat rowFormat = table.FirstRow.RowFormat;
rowFormat.Height = 25;
rowFormat.Borders[BorderType.Bottom].Color = Color.Red;

// Utilisez la propriété "CellFormat" de la première cellule de la dernière ligne pour modifier la mise en forme du contenu de cette cellule.
CellFormat cellFormat = table.LastRow.FirstCell.CellFormat;
cellFormat.Width = 100;
cellFormat.Shading.BackgroundPatternColor = Color.Orange;

doc.Save(ArtifactsDir + "Table.RowCellFormat.docx");
```

### Voir également

* class [RowFormat](../../rowformat/)
* class [Row](../)
* espace de noms [Aspose.Words.Tables](../../row/)
* Assemblée [Aspose.Words](../../../)


