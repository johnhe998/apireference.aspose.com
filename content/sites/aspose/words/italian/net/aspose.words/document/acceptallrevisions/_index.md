---
title: Document.AcceptAllRevisions
second_title: Aspose.Words per .NET API Reference
description: Document metodo. Accetta tutte le modifiche rilevate nel documento.
type: docs
weight: 500
url: /it/net/aspose.words/document/acceptallrevisions/
---
## Document.AcceptAllRevisions method

Accetta tutte le modifiche rilevate nel documento.

```csharp
public void AcceptAllRevisions()
```

### Osservazioni

Questo metodo è una scorciatoia per[`AcceptAll`](../../revisioncollection/acceptall/).

### Esempi

Mostra come accettare tutte le modifiche di rilevamento nel documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Modifica il documento tenendo traccia delle modifiche per creare alcune revisioni.
doc.StartTrackRevisions("John Doe");
builder.Write("Hello world! ");
builder.Write("Hello again! "); 
builder.Write("This is another revision.");
doc.StopTrackRevisions();

Assert.AreEqual(3, doc.Revisions.Count);

// Possiamo scorrere ogni revisione e accettarla/rifiutarla come parte del nostro documento.
// Se sappiamo che desideriamo accettare ogni revisione, possiamo farlo in modo più diretto chiamando questo metodo.
doc.AcceptAllRevisions();

Assert.AreEqual(0, doc.Revisions.Count);
Assert.AreEqual("Hello world! Hello again! This is another revision.", doc.GetText().Trim());
```

### Guarda anche

* class [Document](../)
* spazio dei nomi [Aspose.Words](../../document/)
* assemblea [Aspose.Words](../../../)


