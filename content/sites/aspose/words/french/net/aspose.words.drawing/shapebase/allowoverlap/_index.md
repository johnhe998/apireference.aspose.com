---
title: ShapeBase.AllowOverlap
second_title: Référence de l'API Aspose.Words pour .NET
description: ShapeBase propriété. Obtient ou définit une valeur qui spécifie si cette forme peut chevaucher dautres formes.
type: docs
weight: 10
url: /fr/net/aspose.words.drawing/shapebase/allowoverlap/
---
## ShapeBase.AllowOverlap property

Obtient ou définit une valeur qui spécifie si cette forme peut chevaucher d'autres formes.

```csharp
public bool AllowOverlap { get; set; }
```

### Remarques

Cette propriété affecte le comportement de la forme dans Microsoft Word. Aspose.Words ignore la valeur de cette propriété.

Cette propriété s'applique uniquement aux formes de niveau supérieur.

La valeur par défaut est **vrai**.

### Exemples

Montre comment utiliser les propriétés des tables flottantes.

```csharp
Document doc = new Document(MyDir + "Table wrapped by text.docx");

Table table = doc.FirstSection.Body.Tables[0];

if (table.TextWrapping == TextWrapping.Around)
{
    Assert.AreEqual(RelativeHorizontalPosition.Margin, table.HorizontalAnchor);
    Assert.AreEqual(RelativeVerticalPosition.Paragraph, table.VerticalAnchor);
    Assert.AreEqual(false, table.AllowOverlap);

    // Uniquement Margin, Page, Column disponibles dans RelativeHorizontalPosition pour le setter HorizontalAnchor.
    // L'ArgumentException sera levée pour toutes les autres valeurs.
    table.HorizontalAnchor = RelativeHorizontalPosition.Column;

    // Uniquement Margin, Page, Paragraph disponible dans RelativeVerticalPosition pour le setter VerticalAnchor.
    // L'ArgumentException sera levée pour toutes les autres valeurs.
    table.VerticalAnchor = RelativeVerticalPosition.Page;
}
```

### Voir également

* class [ShapeBase](../)
* espace de noms [Aspose.Words.Drawing](../../shapebase/)
* Assemblée [Aspose.Words](../../../)


