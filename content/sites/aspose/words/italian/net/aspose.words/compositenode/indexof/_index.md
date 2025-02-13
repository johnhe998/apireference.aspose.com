---
title: CompositeNode.IndexOf
second_title: Aspose.Words per .NET API Reference
description: CompositeNode metodo. Restituisce lindice del nodo figlio specificato nellarray del nodo figlio.
type: docs
weight: 130
url: /it/net/aspose.words/compositenode/indexof/
---
## CompositeNode.IndexOf method

Restituisce l'indice del nodo figlio specificato nell'array del nodo figlio.

```csharp
public int IndexOf(Node child)
```

### Osservazioni

Restituisce -1 se il nodo non viene trovato nei nodi figli.

### Esempi

Mostra come ottenere l'indice di un dato nodo figlio dal suo genitore.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

Body body = doc.FirstSection.Body;

// Recupera l'indice dell'ultimo paragrafo nel corpo della prima sezione.
Assert.AreEqual(24, body.ChildNodes.IndexOf(body.LastParagraph));
```

### Guarda anche

* class [Node](../../node/)
* class [CompositeNode](../)
* spazio dei nomi [Aspose.Words](../../compositenode/)
* assemblea [Aspose.Words](../../../)


