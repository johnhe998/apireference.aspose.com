---
title: Comment.Author
second_title: Aspose.Words für .NET-API-Referenz
description: Comment eigendom. Gibt den Autorennamen für einen Kommentar zurück oder legt ihn fest.
type: docs
weight: 30
url: /de/net/aspose.words/comment/author/
---
## Comment.Author property

Gibt den Autorennamen für einen Kommentar zurück oder legt ihn fest.

```csharp
public string Author { get; set; }
```

### Bemerkungen

Kann nicht Null sein.

Standard ist eine leere Zeichenfolge.

### Beispiele

Zeigt, wie alle Kommentare eines Dokuments und ihre Antworten gedruckt werden.

```csharp
Document doc = new Document(MyDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);

// Wenn ein Kommentar keinen Vorfahren hat, handelt es sich um einen "Top-Level"-Kommentar im Gegensatz zu einem Antworttyp-Kommentar.
// Drucken Sie alle Kommentare der obersten Ebene zusammen mit allen möglichen Antworten.
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

### Siehe auch

* class [Comment](../)
* namensraum [Aspose.Words](../../comment/)
* Montage [Aspose.Words](../../../)


