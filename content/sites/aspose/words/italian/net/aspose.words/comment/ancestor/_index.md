---
title: Comment.Ancestor
second_title: Aspose.Words per .NET API Reference
description: Comment proprietà. Restituisce loggetto Commento padre. Restituisce null per i commenti di primo livello.
type: docs
weight: 20
url: /it/net/aspose.words/comment/ancestor/
---
## Comment.Ancestor property

Restituisce l'oggetto Commento padre. Restituisce null per i commenti di primo livello.

```csharp
public Comment Ancestor { get; }
```

### Esempi

Mostra come stampare tutti i commenti di un documento e le relative risposte.

```csharp
Document doc = new Document(MyDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);

// Se un commento non ha predecessori, è un commento di "livello superiore" anziché un commento di tipo risposta.
// Stampa tutti i commenti di primo livello insieme a tutte le risposte che potrebbero avere.
foreach (Comment comment in comments.OfType<Comment>().Where(c => c.Ancestor == null))
{
    Console.WriteLine("Top-level comment:");
    Console.WriteLine($"\t\"{comment.GetText().Trim()}\", by {comment.Author}");
    Console.WriteLine($"Has {comment.Replies.Count} replies");
    foreach (Comment commentReply in comment.Replies)
    {
        Console.WriteLine($"\t\"{commentReply.GetText().Trim()}\", by {commentReply.Author}");
    }
    Console.WriteLine();
}
```

### Guarda anche

* class [Comment](../)
* spazio dei nomi [Aspose.Words](../../comment/)
* assemblea [Aspose.Words](../../../)


