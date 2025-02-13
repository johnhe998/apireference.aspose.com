---
title: Node.PreviousSibling
second_title: Aspose.Words per .NET API Reference
description: Node proprietà. Ottiene il nodo immediatamente precedente a questo nodo.
type: docs
weight: 70
url: /it/net/aspose.words/node/previoussibling/
---
## Node.PreviousSibling property

Ottiene il nodo immediatamente precedente a questo nodo.

```csharp
public Node PreviousSibling { get; }
```

### Osservazioni

Se non è presente alcun nodo precedente, viene restituito un null.

### Esempi

Mostra come utilizzare i metodi di Node e CompositeNode per rimuovere una sezione prima dell'ultima sezione nel documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Section 1 text.");
builder.InsertBreak(BreakType.SectionBreakContinuous);
builder.Writeln("Section 2 text.");

// Entrambe le sezioni sono fratelli l'uno dell'altro.
Section lastSection = (Section)doc.LastChild;
Section firstSection = (Section)lastSection.PreviousSibling;

// Rimuove una sezione in base alla sua relazione di pari livello con un'altra sezione.
if (lastSection.PreviousSibling != null)
    doc.RemoveChild(firstSection);

// La sezione che abbiamo rimosso è stata la prima, lasciando il documento solo con la seconda.
Assert.AreEqual("Section 2 text.", doc.GetText().Trim());
```

### Guarda anche

* class [Node](../)
* spazio dei nomi [Aspose.Words](../../node/)
* assemblea [Aspose.Words](../../../)


