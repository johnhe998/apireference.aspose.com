---
title: Comment.Ancestor
second_title: Aspose.Words för .NET API Referens
description: Comment fast egendom. Returnerar det överordnade kommentarobjektet. Returnerar null för kommentarer på toppnivå.
type: docs
weight: 20
url: /sv/net/aspose.words/comment/ancestor/
---
## Comment.Ancestor property

Returnerar det överordnade kommentarobjektet. Returnerar null för kommentarer på toppnivå.

```csharp
public Comment Ancestor { get; }
```

### Exempel

Visar hur du skriver ut alla kommentarer i ett dokument och deras svar.

```csharp
Document doc = new Document(MyDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);

// Om en kommentar inte har någon förfader är den en kommentar på "toppnivå" i motsats till en kommentar av typen svar.
// Skriv ut alla kommentarer på toppnivå tillsammans med eventuella svar de kan ha.
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

### Se även

* class [Comment](../)
* namnutrymme [Aspose.Words](../../comment/)
* hopsättning [Aspose.Words](../../../)


