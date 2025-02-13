---
title: Class NodeCollection
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.NodeCollection classe. Rappresenta una raccolta di nodi di un tipo specifico.
type: docs
weight: 3960
url: /it/net/aspose.words/nodecollection/
---
## NodeCollection class

Rappresenta una raccolta di nodi di un tipo specifico.

```csharp
public class NodeCollection : IEnumerable<Node>
```

## Proprietà

| Nome | Descrizione |
| --- | --- |
| [Count](../../aspose.words/nodecollection/count/) { get; } | Ottiene il numero di nodi nella raccolta. |
| [Item](../../aspose.words/nodecollection/item/) { get; } | Recupera un nodo in corrispondenza dell'indice specificato. |

## Metodi

| Nome | Descrizione |
| --- | --- |
| [Add](../../aspose.words/nodecollection/add/)(Node) | Aggiunge un nodo alla fine della raccolta. |
| [Clear](../../aspose.words/nodecollection/clear/)() | Rimuove tutti i nodi da questa raccolta e dal documento. |
| [Contains](../../aspose.words/nodecollection/contains/)(Node) | Determina se un nodo è nella raccolta. |
| [GetEnumerator](../../aspose.words/nodecollection/getenumerator/)() | Fornisce una semplice iterazione di stile "foreach" sulla raccolta di nodi. |
| [IndexOf](../../aspose.words/nodecollection/indexof/)(Node) | Restituisce l'indice in base zero del nodo specificato. |
| [Insert](../../aspose.words/nodecollection/insert/)(int, Node) | Inserisce un nodo nella raccolta in corrispondenza dell'indice specificato. |
| [Remove](../../aspose.words/nodecollection/remove/)(Node) | Rimuove il nodo dalla raccolta e dal documento. |
| [RemoveAt](../../aspose.words/nodecollection/removeat/)(int) | Rimuove il nodo in corrispondenza dell'indice specificato dalla raccolta e dal documento. |
| [ToArray](../../aspose.words/nodecollection/toarray/)() | Copia tutti i nodi dalla raccolta in un nuovo array di nodi. |

### Osservazioni

**NodeCollection** non possiede i nodi che contiene, piuttosto, è solo una selezione di nodes del tipo specificato, ma i nodi sono memorizzati nell'albero sotto i rispettivi nodi principali.

**NodeCollection**supporta l'accesso indicizzato, l'iterazione e fornisce metodi di aggiunta e rimozione.

Il **NodeCollection** raccolta è "live", cioè le modifiche ai figli del nodo oggetto da cui è stato creato vengono immediatamente riflesse nei nodi restituiti dal **NodeCollection** proprietà e metodi.

**NodeCollection** viene restituito da[`GetChildNodes`](../compositenode/getchildnodes/) e funge anche da classe base per raccolte di nodi tipizzati come[`SectionCollection`](../sectioncollection/) , [`ParagraphCollection`](../paragraphcollection/) eccetera.

**NodeCollection** può essere "flat" e contenere solo figli immediati del nodo da cui è stato creato , oppure può essere "deep" e contenere tutti i figli discendenti.

### Esempi

Mostra come sostituire tutte le forme casella di testo con forme immagine.

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

### Guarda anche

* class [Node](../node/)
* spazio dei nomi [Aspose.Words](../../aspose.words/)
* assemblea [Aspose.Words](../../)


