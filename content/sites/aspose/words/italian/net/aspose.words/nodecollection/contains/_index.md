---
title: NodeCollection.Contains
second_title: Aspose.Words per .NET API Reference
description: NodeCollection metodo. Determina se un nodo è nella raccolta.
type: docs
weight: 50
url: /it/net/aspose.words/nodecollection/contains/
---
## NodeCollection.Contains method

Determina se un nodo è nella raccolta.

```csharp
public bool Contains(Node node)
```

| Parametro | Tipo | Descrizione |
| --- | --- | --- |
| node | Node | Il nodo da individuare. |

### Valore di ritorno

Vero se l'articolo viene trovato nella collezione; altrimenti falso.

### Osservazioni

Questo metodo esegue una ricerca lineare; pertanto, il tempo medio di esecuzione è proporzionale a Count.

### Esempi

Mostra come lavorare con una NodeCollection.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Aggiungi testo al documento inserendo le esecuzioni utilizzando un DocumentBuilder.
builder.Write("Run 1. ");
builder.Write("Run 2. ");

// Ogni chiamata del metodo "Write" crea un nuovo Run,
// che viene quindi visualizzato nella RunCollection del paragrafo padre.
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;

Assert.AreEqual(2, runs.Count);

// Possiamo anche inserire manualmente un nodo in RunCollection.
Run newRun = new Run(doc, "Run 3. ");
runs.Insert(3, newRun);

Assert.True(runs.Contains(newRun));
Assert.AreEqual("Run 1. Run 2. Run 3.", doc.GetText().Trim());

// Accedi alle singole esecuzioni e rimuovile per rimuovere il testo dal documento.
Run run = runs[1];
runs.Remove(run);

Assert.AreEqual("Run 1. Run 3.", doc.GetText().Trim());
Assert.NotNull(run);
Assert.False(runs.Contains(run));
```

### Guarda anche

* class [Node](../../node/)
* class [NodeCollection](../)
* spazio dei nomi [Aspose.Words](../../nodecollection/)
* assemblea [Aspose.Words](../../../)


