---
title: CellFormat.VerticalMerge
second_title: Référence de l'API Aspose.Words pour .NET
description: CellFormat propriété. Spécifie comment la cellule est fusionnée verticalement avec dautres cellules.
type: docs
weight: 120
url: /fr/net/aspose.words.tables/cellformat/verticalmerge/
---
## CellFormat.VerticalMerge property

Spécifie comment la cellule est fusionnée verticalement avec d'autres cellules.

```csharp
public CellMerge VerticalMerge { get; set; }
```

### Remarques

Les cellules ne peuvent être fusionnées verticalement que si leurs limites gauche et droite sont identiques.

Lorsque les cellules sont fusionnées verticalement, les zones d'affichage des cellules fusionnées sont consolidées. La zone consolidée est utilisée pour afficher le contenu de la première cellule fusionnée verticalement et toutes les autres cellules fusionnées verticalement doivent être vides.

### Exemples

Imprime le type de fusion horizontale et verticale d'une cellule.

```csharp
public void CheckCellsMerged()
{
    Document doc = new Document(MyDir + "Table with merged cells.docx");
    Table table = doc.FirstSection.Body.Tables[0];

    foreach (Row row in table.Rows.OfType<Row>())
        foreach (Cell cell in row.Cells.OfType<Cell>())
            Console.WriteLine(PrintCellMergeType(cell));
}

public string PrintCellMergeType(Cell cell)
{
    bool isHorizontallyMerged = cell.CellFormat.HorizontalMerge != CellMerge.None;
    bool isVerticallyMerged = cell.CellFormat.VerticalMerge != CellMerge.None;
    string cellLocation =
        $"R{cell.ParentRow.ParentTable.IndexOf(cell.ParentRow) + 1}, C{cell.ParentRow.IndexOf(cell) + 1}";

    if (isHorizontallyMerged && isVerticallyMerged)
        return $"The cell at {cellLocation} is both horizontally and vertically merged";
    if (isHorizontallyMerged)
        return $"The cell at {cellLocation} is horizontally merged.";

    return isVerticallyMerged ? $"The cell at {cellLocation} is vertically merged" : $"The cell at {cellLocation} is not merged";
}
```

Montre comment fusionner verticalement des cellules de tableau.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insère une cellule dans la première colonne de la première ligne.
// Cette cellule sera la première d'une série de cellules fusionnées verticalement.
builder.InsertCell();
builder.CellFormat.VerticalMerge = CellMerge.First;
builder.Write("Text in merged cells.");

// Insère une cellule dans la deuxième colonne de la première ligne, puis termine la ligne.
// Configurez également le générateur pour désactiver la fusion verticale dans les cellules créées.
builder.InsertCell();
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in unmerged cell.");
builder.EndRow();

// Insère une cellule dans la première colonne de la deuxième ligne. 
// Au lieu d'ajouter du contenu textuel, nous fusionnerons cette cellule avec la première cellule que nous avons ajoutée directement au-dessus.
builder.InsertCell();
builder.CellFormat.VerticalMerge = CellMerge.Previous;

// Insère une autre cellule indépendante dans la deuxième colonne de la deuxième ligne.
builder.InsertCell();
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in unmerged cell.");
builder.EndRow();
builder.EndTable();

doc.Save(ArtifactsDir + "CellFormat.VerticalMerge.docx");
```

### Voir également

* enum [CellMerge](../../cellmerge/)
* class [CellFormat](../)
* espace de noms [Aspose.Words.Tables](../../cellformat/)
* Assemblée [Aspose.Words](../../../)


