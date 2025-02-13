---
title: ShapeBase.Title
second_title: Aspose.Words für .NET-API-Referenz
description: ShapeBase eigendom. Ruft den Titel Beschriftung des aktuellen Formobjekts ab oder legt ihn fest.
type: docs
weight: 490
url: /de/net/aspose.words.drawing/shapebase/title/
---
## ShapeBase.Title property

Ruft den Titel (Beschriftung) des aktuellen Formobjekts ab oder legt ihn fest.

```csharp
public string Title { get; set; }
```

### Bemerkungen

Standard ist eine leere Zeichenfolge.

Kann nicht null sein, kann aber eine leere Zeichenfolge sein.

### Beispiele

Zeigt, wie der Titel einer Form festgelegt wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Erstellen Sie eine Form, geben Sie ihr einen Titel und fügen Sie sie dann dem Dokument hinzu.
Shape shape = new Shape(doc, ShapeType.Cube);
shape.Width = 200;
shape.Height = 200;
shape.Title = "My cube";

builder.InsertNode(shape);

// Wenn wir ein Dokument mit einer Form speichern, die einen Titel hat,
// Aspose.Words speichert diesen Titel im Alt-Text der Form.
doc.Save(ArtifactsDir + "Shape.Title.docx");

doc = new Document(ArtifactsDir + "Shape.Title.docx");
shape = (Shape)doc.GetChild(NodeType.Shape, 0, true);

Assert.AreEqual(string.Empty, shape.Title);
Assert.AreEqual("Title: My cube", shape.AlternativeText);
```

### Siehe auch

* class [ShapeBase](../)
* namensraum [Aspose.Words.Drawing](../../shapebase/)
* Montage [Aspose.Words](../../../)


