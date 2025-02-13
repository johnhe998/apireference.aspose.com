---
title: CommentCollection.Item
second_title: Aspose.Words per .NET API Reference
description: CommentCollection proprietà. Recupera a Commento allindice dato.
type: docs
weight: 10
url: /it/net/aspose.words/commentcollection/item/
---
## CommentCollection indexer

Recupera a **Commento** all'indice dato.

```csharp
public Comment this[int index] { get; }
```

| Parametro | Descrizione |
| --- | --- |
| index | Un indice nella raccolta. |

### Osservazioni

L'indice è a base zero.

Gli indici negativi sono consentiti e indicano l'accesso dal retro della raccolta. Ad esempio -1 indica l'ultimo elemento, -2 indica il penultimo e così via.

Se l'indice è maggiore o uguale al numero di elementi nell'elenco, restituisce un riferimento nullo.

Se l'indice è negativo e il suo valore assoluto è maggiore del numero di elementi nell'elenco, restituisce un riferimento nullo.

### Esempi

Mostra come rimuovere le risposte ai commenti.

```csharp
Document doc = new Document();

Comment comment = new Comment(doc, "John Doe", "J.D.", DateTime.Now);
comment.SetText("My comment.");

doc.FirstSection.Body.FirstParagraph.AppendChild(comment);

comment.AddReply("Joe Bloggs", "J.B.", DateTime.Now, "New reply");
comment.AddReply("Joe Bloggs", "J.B.", DateTime.Now, "Another reply");

Assert.AreEqual(2, comment.Replies.Count()); 

// Di seguito sono riportati due modi per rimuovere le risposte da un commento.
// 1 - Usa il metodo "RemoveReply" per rimuovere le risposte da un commento singolarmente:
comment.RemoveReply(comment.Replies[0]);

Assert.AreEqual(1, comment.Replies.Count());

// 2 - Usa il metodo "RemoveAllReplies" per rimuovere tutte le risposte da un commento contemporaneamente:
comment.RemoveAllReplies();

Assert.AreEqual(0, comment.Replies.Count());
```

### Guarda anche

* class [Comment](../../comment/)
* class [CommentCollection](../)
* spazio dei nomi [Aspose.Words](../../commentcollection/)
* assemblea [Aspose.Words](../../../)


