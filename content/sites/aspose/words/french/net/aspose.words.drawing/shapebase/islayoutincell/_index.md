---
title: ShapeBase.IsLayoutInCell
second_title: Référence de l'API Aspose.Words pour .NET
description: ShapeBase propriété. Obtient ou définit un indicateur indiquant si la forme est affichée à lintérieur ou à lextérieur dun tableau.
type: docs
weight: 300
url: /fr/net/aspose.words.drawing/shapebase/islayoutincell/
---
## ShapeBase.IsLayoutInCell property

Obtient ou définit un indicateur indiquant si la forme est affichée à l'intérieur ou à l'extérieur d'un tableau.

```csharp
public bool IsLayoutInCell { get; set; }
```

### Remarques

La valeur par défaut est **vrai**.

N'a d'effet que pour les formes de niveau supérieur, la propriété[`WrapType`](../wraptype/) dont est défini sur value autre que[`Inline`](../../../aspose.words/inline/).

### Exemples

Montre comment déterminer comment afficher une forme dans une cellule de tableau.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
builder.InsertCell();
builder.EndTable();

TableStyle tableStyle = (TableStyle)doc.Styles.Add(StyleType.Table, "MyTableStyle1");
tableStyle.BottomPadding = 20;
tableStyle.LeftPadding = 10;
tableStyle.RightPadding = 10;
tableStyle.TopPadding = 20;
tableStyle.Borders.Color = Color.Black;
tableStyle.Borders.LineStyle = LineStyle.Single;

table.Style = tableStyle;

builder.MoveTo(table.FirstRow.FirstCell.FirstParagraph);

Shape shape = builder.InsertShape(ShapeType.Rectangle, RelativeHorizontalPosition.LeftMargin, 50,
    RelativeVerticalPosition.TopMargin, 100, 100, 100, WrapType.None);

// Définissez la propriété "IsLayoutInCell" sur "true" pour afficher la forme en tant qu'élément en ligne à l'intérieur du paragraphe de la cellule.
// L'origine des coordonnées qui déterminera l'emplacement de la forme sera le coin supérieur gauche de la cellule de la forme.
// Si nous redimensionnons la cellule, la forme se déplacera pour conserver la même position en partant du haut à gauche de la cellule.
// Définissez la propriété "IsLayoutInCell" sur "false" pour afficher la forme en tant que forme flottante indépendante.
// L'origine des coordonnées qui déterminera l'emplacement de la forme sera le coin supérieur gauche de la page,
// et la forme ne répondra à aucun redimensionnement de sa cellule.
shape.IsLayoutInCell = isLayoutInCell;

// Nous ne pouvons appliquer la propriété "IsLayoutInCell" qu'aux formes flottantes.
shape.WrapType = WrapType.None;

doc.Save(ArtifactsDir + "Shape.LayoutInTableCell.docx");
```

### Voir également

* class [ShapeBase](../)
* espace de noms [Aspose.Words.Drawing](../../shapebase/)
* Assemblée [Aspose.Words](../../../)


