---
title: CompositeNode.GetChild
second_title: Aspose.Words per .NET API Reference
description: CompositeNode metodo. Restituisce un ennesimo nodo figlio che corrisponde al tipo specificato.
type: docs
weight: 90
url: /it/net/aspose.words/compositenode/getchild/
---
## CompositeNode.GetChild method

Restituisce un ennesimo nodo figlio che corrisponde al tipo specificato.

```csharp
public Node GetChild(NodeType nodeType, int index, bool isDeep)
```

| Parametro | Tipo | Descrizione |
| --- | --- | --- |
| nodeType | NodeType | Specifica il tipo del nodo figlio. |
| index | Int32 | Indice in base zero del nodo figlio da selezionare. Sono consentiti anche indici negativi e indicano l'accesso dalla fine, ovvero -1 indica l'ultimo nodo. |
| isDeep | Boolean | True per selezionare ricorsivamente da tutti i nodi figli. False per selezionare solo tra i figli immediati. Vedi le osservazioni per maggiori informazioni. |

### Valore di ritorno

Il nodo figlio che corrisponde ai criteri o null se non viene trovato alcun nodo corrispondente.

### Osservazioni

Se l'indice non è compreso nell'intervallo, viene restituito un valore null.

Nota che i nodi di markup (StructuredDocumentTag eSmartTag) vengono attraversati anche quando isDeep = false e GetChild viene richiamato per un tipo di nodo non di markup. Ad esempio, se la prima esecuzione in un parametro è racchiusa in un StructuredDocumentTag, verrà comunque restituita da GetChild(NodeType.Run, 0, false).

### Esempi

Mostra come applicare le proprietà dello stile di una tabella direttamente agli elementi della tabella.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Hello world!");
builder.EndTable();

TableStyle tableStyle = (TableStyle)doc.Styles.Add(StyleType.Table, "MyTableStyle1");
tableStyle.RowStripe = 3;
tableStyle.CellSpacing = 5;
tableStyle.Shading.BackgroundPatternColor = Color.AntiqueWhite;
tableStyle.Borders.Color = Color.Blue;
tableStyle.Borders.LineStyle = LineStyle.DotDash;

table.Style = tableStyle;

// Questo metodo riguarda le proprietà dello stile della tabella come quelle impostate sopra.
doc.ExpandTableStylesToDirectFormatting();

doc.Save(ArtifactsDir + "Document.TableStyleToDirectFormatting.docx");
```

Mostra come attraversare la raccolta di nodi figlio di un nodo composito.

```csharp
Document doc = new Document();

// Aggiungi due esecuzioni e una forma come nodi figlio al primo paragrafo di questo documento.
Paragraph paragraph = (Paragraph)doc.GetChild(NodeType.Paragraph, 0, true);
paragraph.AppendChild(new Run(doc, "Hello world! "));

Shape shape = new Shape(doc, ShapeType.Rectangle);
shape.Width = 200;
shape.Height = 200;
// Nota che 'CustomNodeId' non viene salvato in un file di output ed esiste solo durante la vita del nodo.
shape.CustomNodeId = 100;
shape.WrapType = WrapType.Inline;
paragraph.AppendChild(shape);

paragraph.AppendChild(new Run(doc, "Hello again!"));

// Scorri la raccolta del paragrafo dei figli immediati,
// e stampa qualsiasi traccia o forma che troviamo all'interno.
NodeCollection children = paragraph.ChildNodes;

Assert.AreEqual(3, paragraph.ChildNodes.Count);

foreach (Node child in children)
    switch (child.NodeType)
    {
        case NodeType.Run:
            Console.WriteLine("Run contents:");
            Console.WriteLine($"\t\"{child.GetText().Trim()}\"");
            break;
        case NodeType.Shape:
            Shape childShape = (Shape)child;
            Console.WriteLine("Shape:");
            Console.WriteLine($"\t{childShape.ShapeType}, {childShape.Width}x{childShape.Height}");
    }
```

### Guarda anche

* class [Node](../../node/)
* enum [NodeType](../../nodetype/)
* class [CompositeNode](../)
* spazio dei nomi [Aspose.Words](../../compositenode/)
* assemblea [Aspose.Words](../../../)


