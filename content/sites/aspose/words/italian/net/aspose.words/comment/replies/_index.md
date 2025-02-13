---
title: Comment.Replies
second_title: Aspose.Words per .NET API Reference
description: Comment proprietà. Restituisce una raccolta diComment oggetti che sono figli immediati del commento specificato.
type: docs
weight: 90
url: /it/net/aspose.words/comment/replies/
---
## Comment.Replies property

Restituisce una raccolta di[`Comment`](../) oggetti che sono figli immediati del commento specificato.

```csharp
public CommentCollection Replies { get; }
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

* class [CommentCollection](../../commentcollection/)
* class [Comment](../)
* spazio dei nomi [Aspose.Words](../../comment/)
* assemblea [Aspose.Words](../../../)


