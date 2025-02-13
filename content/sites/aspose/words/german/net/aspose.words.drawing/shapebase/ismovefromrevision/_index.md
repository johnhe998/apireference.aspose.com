---
title: ShapeBase.IsMoveFromRevision
second_title: Aspose.Words für .NET-API-Referenz
description: ShapeBase eigendom. gibt zurück Stimmt wenn dieses Objekt in Microsoft Word verschoben gelöscht wurde während die Änderungsnachverfolgung aktiviert war.
type: docs
weight: 310
url: /de/net/aspose.words.drawing/shapebase/ismovefromrevision/
---
## ShapeBase.IsMoveFromRevision property

gibt zurück **Stimmt** wenn dieses Objekt in Microsoft Word verschoben (gelöscht) wurde, während die Änderungsnachverfolgung aktiviert war.

```csharp
public bool IsMoveFromRevision { get; }
```

### Beispiele

Zeigt, wie Änderungsformen für Verschiebungen identifiziert werden.

```csharp
// Eine Move-Revision ist, wenn wir ein Element im Textkörper des Dokuments verschieben, indem wir es in Microsoft Word ausschneiden und einfügen
// Änderungen verfolgen. Wenn wir eine Inline-Form in eine solche Textbewegung einbeziehen, wird diese Form auch eine Überarbeitung sein.
// Das Kopieren und Einfügen oder das Verschieben schwebender Formen erzeugt keine Verschiebungsrevisionen.
Document doc = new Document(MyDir + "Revision shape.docx");

// Verschiebungsrevisionen bestehen aus Paaren von "Move from"- und "Move to"-Revisionen. Wir haben uns in diesem Dokument in einer Form bewegt,
// aber bis wir die Move-Revision akzeptieren oder ablehnen, wird es zwei Instanzen dieser Form geben.
Shape[] shapes = doc.GetChildNodes(NodeType.Shape, true).OfType<Shape>().ToArray();

Assert.AreEqual(2, shapes.Length);

// Dies ist die "Move to"-Revision, die die Form an ihrem Ankunftsziel ist.
// Wenn wir die Revision akzeptieren, verschwindet diese Revisionsform "Verschieben nach",
// und die Revisionsform "Move from" bleibt bestehen.
Assert.False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

// Dies ist die "Move from"-Revision, also die Form an ihrer ursprünglichen Position.
// Wenn wir die Revision akzeptieren, verschwindet diese "Move from"-Revisionsform,
// und die Revisionsform "Verschieben nach" bleibt bestehen.
Assert.True(shapes[1].IsMoveFromRevision);
Assert.False(shapes[1].IsMoveToRevision);
```

### Siehe auch

* class [ShapeBase](../)
* namensraum [Aspose.Words.Drawing](../../shapebase/)
* Montage [Aspose.Words](../../../)


