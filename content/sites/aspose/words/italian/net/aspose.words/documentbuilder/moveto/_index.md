---
title: DocumentBuilder.MoveTo
second_title: Aspose.Words per .NET API Reference
description: DocumentBuilder metodo. Sposta il cursore su un nodo in linea o alla fine di un paragrafo.
type: docs
weight: 460
url: /it/net/aspose.words/documentbuilder/moveto/
---
## DocumentBuilder.MoveTo method

Sposta il cursore su un nodo in linea o alla fine di un paragrafo.

```csharp
public void MoveTo(Node node)
```

| Parametro | Tipo | Descrizione |
| --- | --- | --- |
| node | Node | Il nodo deve essere un paragrafo o un figlio diretto di un paragrafo. |

### Osservazioni

quandonodo è un nodo a livello inline, il cursore viene spostato su questo nodo e ulteriore contenuto verrà inserito prima di quel nodo.

quandonodo è un **Paragrafo**, il cursore viene spostato alla fine del paragrafo e altro contenuto verrà inserito appena prima dell'interruzione del paragrafo.

quandonodoè un nodo a livello di blocco ma non un paragrafo, il cursore viene spostato alla fine del primo paragrafo nel nodo a livello di blocco e ulteriore contenuto verrà inserito appena prima dell'interruzione del paragrafo.

### Esempi

Mostra come spostare la posizione del cursore di un DocumentBuilder su un nodo specificato.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Run 1. ");

// Il generatore di documenti ha un cursore, che funge da parte del documento
// dove il builder aggiunge nuovi nodi quando utilizziamo i suoi metodi di costruzione del documento.
// Questo cursore funziona allo stesso modo del cursore lampeggiante di Microsoft Word,
// e finisce sempre subito dopo ogni nodo che il builder ha appena inserito.
// Per aggiungere contenuto a una parte diversa del documento,
// possiamo spostare il cursore su un nodo diverso con il metodo "MoveTo".
// Il cursore ora si trova davanti al nodo in cui lo abbiamo spostato.
// L'aggiunta di una seconda esecuzione la inserirà davanti alla prima.
builder.Writeln("Run 2. ");

Assert.AreEqual("Run 2. \rRun 1.", doc.GetText().Trim());

// Sposta il cursore alla fine del documento per continuare ad aggiungere il testo alla fine come prima.
builder.MoveTo(doc.LastSection.Body.LastParagraph);
builder.Writeln("Run 3. ");

Assert.AreEqual("Run 2. \rRun 1. \rRun 3.", doc.GetText().Trim());
```

Mostra come spostare il cursore di un generatore di documenti su nodi diversi in un documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Crea un segnalibro valido, un'entità composta da nodi racchiusi da un nodo di inizio segnalibro,
 // e un nodo finale del segnalibro.
builder.StartBookmark("MyBookmark");
builder.Write("Bookmark contents.");
builder.EndBookmark("MyBookmark");

NodeCollection firstParagraphNodes = doc.FirstSection.Body.FirstParagraph.ChildNodes;

Assert.AreEqual(NodeType.BookmarkStart, firstParagraphNodes[0].NodeType);
Assert.AreEqual(NodeType.Run, firstParagraphNodes[1].NodeType);
Assert.AreEqual("Bookmark contents.", firstParagraphNodes[1].GetText().Trim());
Assert.AreEqual(NodeType.BookmarkEnd, firstParagraphNodes[2].NodeType);

// Il cursore del generatore di documenti è sempre davanti al nodo che abbiamo aggiunto per ultimo con esso.
// Se il cursore del builder si trova alla fine del documento, il suo nodo corrente sarà nullo.
// Il nodo precedente è il nodo finale del segnalibro che abbiamo aggiunto per ultimo.
// L'aggiunta di nuovi nodi con il builder li aggiungerà all'ultimo nodo.
Assert.Null(builder.CurrentNode);

// Se desideriamo modificare una parte diversa del documento con il builder,
// dovremo portare il cursore sul nodo che desideriamo modificare.
builder.MoveToBookmark("MyBookmark");

// Lo spostamento in un segnalibro lo sposterà sul primo nodo all'interno dei nodi di inizio e fine del segnalibro, la corsa racchiusa.
Assert.AreEqual(firstParagraphNodes[1], builder.CurrentNode);

// Possiamo anche spostare il cursore su un singolo nodo come questo.
builder.MoveTo(doc.FirstSection.Body.FirstParagraph.GetChildNodes(NodeType.Any, false)[0]);

Assert.AreEqual(NodeType.BookmarkStart, builder.CurrentNode.NodeType);
Assert.AreEqual(doc.FirstSection.Body.FirstParagraph, builder.CurrentParagraph);
Assert.IsTrue(builder.IsAtStartOfParagraph);

// Possiamo usare metodi specifici per spostarci all'inizio/alla fine di un documento.
builder.MoveToDocumentEnd();

Assert.IsTrue(builder.IsAtEndOfParagraph);

builder.MoveToDocumentStart();

Assert.IsTrue(builder.IsAtStartOfParagraph);
```

### Guarda anche

* class [Node](../../node/)
* class [DocumentBuilder](../)
* spazio dei nomi [Aspose.Words](../../documentbuilder/)
* assemblea [Aspose.Words](../../../)


