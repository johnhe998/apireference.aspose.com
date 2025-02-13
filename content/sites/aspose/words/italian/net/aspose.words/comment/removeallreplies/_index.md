---
title: Comment.RemoveAllReplies
second_title: Aspose.Words per .NET API Reference
description: Comment metodo. Rimuove tutte le risposte a questo commento.
type: docs
weight: 130
url: /it/net/aspose.words/comment/removeallreplies/
---
## Comment.RemoveAllReplies method

Rimuove tutte le risposte a questo commento.

```csharp
public void RemoveAllReplies()
```

### Osservazioni

Tutti i nodi costitutivi delle risposte verranno eliminati dal documento.

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

* class [Comment](../)
* spazio dei nomi [Aspose.Words](../../comment/)
* assemblea [Aspose.Words](../../../)


