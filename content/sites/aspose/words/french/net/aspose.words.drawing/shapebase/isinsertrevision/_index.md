---
title: ShapeBase.IsInsertRevision
second_title: Référence de l'API Aspose.Words pour .NET
description: ShapeBase propriété. Renvoie true si cet objet a été inséré dans Microsoft Word alors que le suivi des modifications était activé.
type: docs
weight: 290
url: /fr/net/aspose.words.drawing/shapebase/isinsertrevision/
---
## ShapeBase.IsInsertRevision property

Renvoie true si cet objet a été inséré dans Microsoft Word alors que le suivi des modifications était activé.

```csharp
public bool IsInsertRevision { get; }
```

### Exemples

Montre comment travailler avec des formes de révision.

```csharp
Document doc = new Document();

Assert.False(doc.TrackRevisions);

// Insère une forme en ligne sans suivre les révisions, ce qui fera de cette forme une révision d'aucune sorte.
Shape shape = new Shape(doc, ShapeType.Cube);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

// Démarrez le suivi des révisions, puis insérez une autre forme, qui sera une révision.
doc.StartTrackRevisions("John Doe");

shape = new Shape(doc, ShapeType.Sun);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

Shape[] shapes = doc.GetChildNodes(NodeType.Shape, true).OfType<Shape>().ToArray();

Assert.AreEqual(2, shapes.Length);

shapes[0].Remove();

// Puisque nous avons supprimé cette forme pendant que nous suivions les modifications,
// la forme persiste dans le document et compte comme une révision de suppression.
// Accepter cette révision supprimera définitivement la forme, et la rejeter la conservera dans le document.
Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

// Et nous avons inséré une autre forme lors du suivi des modifications, de sorte que cette forme comptera comme une révision d'insertion.
// Accepter cette révision assimilera cette forme dans le document comme une non-révision,
// et rejeter la révision supprimera définitivement cette forme.
Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

### Voir également

* class [ShapeBase](../)
* espace de noms [Aspose.Words.Drawing](../../shapebase/)
* Assemblée [Aspose.Words](../../../)


