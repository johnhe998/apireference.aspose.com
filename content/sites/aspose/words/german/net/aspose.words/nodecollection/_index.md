---
title: Class NodeCollection
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.NodeCollection klas. Repräsentiert eine Sammlung von Knoten eines bestimmten Typs.
type: docs
weight: 3960
url: /de/net/aspose.words/nodecollection/
---
## NodeCollection class

Repräsentiert eine Sammlung von Knoten eines bestimmten Typs.

```csharp
public class NodeCollection : IEnumerable<Node>
```

## Eigenschaften

| Name | Beschreibung |
| --- | --- |
| [Count](../../aspose.words/nodecollection/count/) { get; } | Ruft die Anzahl der Knoten in der Sammlung ab. |
| [Item](../../aspose.words/nodecollection/item/) { get; } | Ruft einen Knoten am angegebenen Index ab. |

## Methoden

| Name | Beschreibung |
| --- | --- |
| [Add](../../aspose.words/nodecollection/add/)(Node) | Fügt am Ende der Sammlung einen Knoten hinzu. |
| [Clear](../../aspose.words/nodecollection/clear/)() | Entfernt alle Knoten aus dieser Sammlung und aus dem Dokument. |
| [Contains](../../aspose.words/nodecollection/contains/)(Node) | Bestimmt, ob sich ein Knoten in der Sammlung befindet. |
| [GetEnumerator](../../aspose.words/nodecollection/getenumerator/)() | Bietet eine einfache Iteration im "foreach"-Stil über die Sammlung von Knoten. |
| [IndexOf](../../aspose.words/nodecollection/indexof/)(Node) | Gibt den nullbasierten Index des angegebenen Knotens zurück. |
| [Insert](../../aspose.words/nodecollection/insert/)(int, Node) | Fügt am angegebenen Index einen Knoten in die Sammlung ein. |
| [Remove](../../aspose.words/nodecollection/remove/)(Node) | Entfernt den Knoten aus der Sammlung und aus dem Dokument. |
| [RemoveAt](../../aspose.words/nodecollection/removeat/)(int) | Entfernt den Knoten am angegebenen Index aus der Sammlung und aus dem Dokument. |
| [ToArray](../../aspose.words/nodecollection/toarray/)() | Kopiert alle Knoten aus der Sammlung in ein neues Array von Knoten. |

### Bemerkungen

**NodeCollection** besitzt nicht die darin enthaltenen Knoten, sondern ist nur eine Auswahl von nodes des angegebenen Typs, aber die Knoten werden im Baum unter ihren jeweiligen übergeordneten Knoten gespeichert.

**NodeCollection**unterstützt indizierten Zugriff, Iteration und bietet Methoden zum Hinzufügen und Entfernen.

Das **NodeCollection** -Sammlung ist "live", dh Änderungen an den Kindern des Knotens object , aus dem sie erstellt wurde, werden sofort in den von zurückgegebenen Knoten widergespiegelt **NodeCollection** Eigenschaften und Methoden.

**NodeCollection** wird von zurückgegeben[`GetChildNodes`](../compositenode/getchildnodes/) und dient auch als Basisklasse für typisierte Knotensammlungen wie z[`SectionCollection`](../sectioncollection/) , [`ParagraphCollection`](../paragraphcollection/) usw.

**NodeCollection** kann "flach" sein und nur unmittelbare Kinder des Knotens enthalten, aus dem er erstellt wurde , oder er kann "tief" sein und alle untergeordneten untergeordneten Knoten enthalten.

### Beispiele

Zeigt, wie alle Textfeldformen durch Bildformen ersetzt werden.

```csharp
Document doc = new Document(MyDir + "Textboxes in drawing canvas.docx");

Shape[] shapes = doc.GetChildNodes(NodeType.Shape, true).OfType<Shape>().ToArray();

Assert.AreEqual(3, shapes.Count(s => s.ShapeType == ShapeType.TextBox));
Assert.AreEqual(1, shapes.Count(s => s.ShapeType == ShapeType.Image));

foreach (Shape shape in shapes)
{
    if (shape.ShapeType == ShapeType.TextBox)
    {
        Shape replacementShape = new Shape(doc, ShapeType.Image);
        replacementShape.ImageData.SetImage(ImageDir + "Logo.jpg");
        replacementShape.Left = shape.Left;
        replacementShape.Top = shape.Top;
        replacementShape.Width = shape.Width;
        replacementShape.Height = shape.Height;
        replacementShape.RelativeHorizontalPosition = shape.RelativeHorizontalPosition;
        replacementShape.RelativeVerticalPosition = shape.RelativeVerticalPosition;
        replacementShape.HorizontalAlignment = shape.HorizontalAlignment;
        replacementShape.VerticalAlignment = shape.VerticalAlignment;
        replacementShape.WrapType = shape.WrapType;
        replacementShape.WrapSide = shape.WrapSide;

        shape.ParentNode.InsertAfter(replacementShape, shape);
        shape.Remove();
    }
}

shapes = doc.GetChildNodes(NodeType.Shape, true).OfType<Shape>().ToArray();

Assert.AreEqual(0, shapes.Count(s => s.ShapeType == ShapeType.TextBox));
Assert.AreEqual(4, shapes.Count(s => s.ShapeType == ShapeType.Image));

doc.Save(ArtifactsDir + "Shape.ReplaceTextboxesWithImages.docx");
```

### Siehe auch

* class [Node](../node/)
* namensraum [Aspose.Words](../../aspose.words/)
* Montage [Aspose.Words](../../)


