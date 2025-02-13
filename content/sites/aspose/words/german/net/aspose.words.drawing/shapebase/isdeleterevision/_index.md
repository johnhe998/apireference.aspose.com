---
title: ShapeBase.IsDeleteRevision
second_title: Aspose.Words für .NET-API-Referenz
description: ShapeBase eigendom. Gibt true zurück wenn dieses Objekt in Microsoft Word gelöscht wurde während die Änderungsnachverfolgung aktiviert war.
type: docs
weight: 240
url: /de/net/aspose.words.drawing/shapebase/isdeleterevision/
---
## ShapeBase.IsDeleteRevision property

Gibt „true“ zurück, wenn dieses Objekt in Microsoft Word gelöscht wurde, während die Änderungsnachverfolgung aktiviert war.

```csharp
public bool IsDeleteRevision { get; }
```

### Beispiele

Zeigt, wie mit Revisionsformen gearbeitet wird.

```csharp
Document doc = new Document();

Assert.False(doc.TrackRevisions);

// Fügen Sie eine Inline-Form ohne Nachverfolgung von Revisionen ein, wodurch diese Form zu keiner Art von Revision wird.
Shape shape = new Shape(doc, ShapeType.Cube);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

// Starten Sie die Verfolgung von Revisionen und fügen Sie dann eine andere Form ein, die eine Revision sein wird.
doc.StartTrackRevisions("John Doe");

shape = new Shape(doc, ShapeType.Sun);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

Shape[] shapes = doc.GetChildNodes(NodeType.Shape, true).OfType<Shape>().ToArray();

Assert.AreEqual(2, shapes.Length);

shapes[0].Remove();

// Da wir diese Form entfernt haben, während wir Änderungen nachverfolgt haben,
// Die Form bleibt im Dokument bestehen und zählt als gelöschte Revision.
// Wenn Sie diese Überarbeitung akzeptieren, wird die Form dauerhaft entfernt, und wenn Sie sie ablehnen, bleibt sie im Dokument.
Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

// Und wir haben eine andere Form eingefügt, während wir Änderungen nachverfolgt haben, sodass diese Form als Einfügungsrevision zählt.
// Wenn Sie diese Revision akzeptieren, wird diese Form als Nicht-Revision in das Dokument aufgenommen,
// und das Ablehnen der Überarbeitung wird diese Form dauerhaft entfernen.
Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

### Siehe auch

* class [ShapeBase](../)
* namensraum [Aspose.Words.Drawing](../../shapebase/)
* Montage [Aspose.Words](../../../)


