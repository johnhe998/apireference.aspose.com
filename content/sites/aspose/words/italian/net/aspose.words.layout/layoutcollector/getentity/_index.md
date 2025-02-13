---
title: LayoutCollector.GetEntity
second_title: Aspose.Words per .NET API Reference
description: LayoutCollector metodo. Restituisce una posizione opaca diLayoutEnumerator che corrisponde al nodo specificato. È possibile utilizzare il valore restituito come argomento perCurrent dato che il documento viene enumerato e il documento del nodo sono gli stessi.
type: docs
weight: 50
url: /it/net/aspose.words.layout/layoutcollector/getentity/
---
## LayoutCollector.GetEntity method

Restituisce una posizione opaca di[`LayoutEnumerator`](../../layoutenumerator/) che corrisponde al nodo specificato. È possibile utilizzare il valore restituito come argomento per[`Current`](../../layoutenumerator/current/) dato che il documento viene enumerato e il documento del nodo sono gli stessi.

```csharp
public object GetEntity(Node node)
```

### Osservazioni

Questo metodo funziona solo per[`Paragraph`](../../../aspose.words/paragraph/) nodi, nonché nodi inline indivisibili, es[`BookmarkStart`](../../../aspose.words/bookmarkstart/) o[`Shape`](../../../aspose.words.drawing/shape/) Non funziona per[`Run`](../../../aspose.words/run/) ,[`Cell`](../../../aspose.words.tables/cell/)[`Row`](../../../aspose.words.tables/row/) o[`Table`](../../../aspose.words.tables/table/) nodi e nodi all'interno di intestazione/piè di pagina.

Si noti che l'entità restituita per a[`Paragraph`](../../../aspose.words/paragraph/) node è un intervallo di interruzione di paragrafo. Utilizzare il metodo appropriato per ascendere alla linea padre

Se hai bisogno di navigare su a[`Run`](../../../aspose.words/run/) di testo, quindi puoi inserire il segnalibro subito prima di esso e quindi passare al segnalibro.

Se hai bisogno di navigare su a[`Cell`](../../../aspose.words.tables/cell/) nodo quindi puoi passare a a[`Paragraph`](../../../aspose.words/paragraph/) in questa cella e quindi ascendere a un'entità padre. Lo stesso approccio può essere utilizzato per[`Row`](../../../aspose.words.tables/row/) e[`Table`](../../../aspose.words.tables/table/) nodi.

### Esempi

Mostra come visualizzare gli intervalli di pagine su cui si estende un nodo.

```csharp
Document doc = new Document();
LayoutCollector layoutCollector = new LayoutCollector(doc);

// Chiama il metodo "GetNumPagesSpanned" per contare quante pagine si estende il contenuto del nostro documento.
// Poiché il documento è vuoto, il numero di pagine attualmente è zero.
Assert.AreEqual(doc, layoutCollector.Document);
Assert.AreEqual(0, layoutCollector.GetNumPagesSpanned(doc));

// Popolare il documento con 5 pagine di contenuto.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Section 1");
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakEvenPage);
builder.Write("Section 2");
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.PageBreak);

// Prima del raccoglitore di layout, dobbiamo chiamare il metodo "UpdatePageLayout" per fornirci
// una cifra precisa per qualsiasi metrica relativa al layout, come il conteggio delle pagine.
Assert.AreEqual(0, layoutCollector.GetNumPagesSpanned(doc));

layoutCollector.Clear();
doc.UpdatePageLayout();

Assert.AreEqual(5, layoutCollector.GetNumPagesSpanned(doc));

// Possiamo vedere i numeri delle pagine iniziali e finali di qualsiasi nodo e le loro estensioni di pagina complessive.
NodeCollection nodes = doc.GetChildNodes(NodeType.Any, true);
foreach (Node node in nodes)
{
    Console.WriteLine($"->  NodeType.{node.NodeType}: ");
    Console.WriteLine(
        $"\tStarts on page {layoutCollector.GetStartPageIndex(node)}, ends on page {layoutCollector.GetEndPageIndex(node)}," +
        $" spanning {layoutCollector.GetNumPagesSpanned(node)} pages.");
}

// Possiamo scorrere le entità del layout usando un LayoutEnumerator.
LayoutEnumerator layoutEnumerator = new LayoutEnumerator(doc);

Assert.AreEqual(LayoutEntityType.Page, layoutEnumerator.Type);

// LayoutEnumerator può attraversare la raccolta di entità di layout come un albero.
// Possiamo anche applicarlo all'entità di layout corrispondente di qualsiasi nodo.
layoutEnumerator.Current = layoutCollector.GetEntity(doc.GetChild(NodeType.Paragraph, 1, true));

Assert.AreEqual(LayoutEntityType.Span, layoutEnumerator.Type);
Assert.AreEqual("¶", layoutEnumerator.Text);
```

### Guarda anche

* class [Node](../../../aspose.words/node/)
* class [LayoutCollector](../)
* spazio dei nomi [Aspose.Words.Layout](../../layoutcollector/)
* assemblea [Aspose.Words](../../../)


