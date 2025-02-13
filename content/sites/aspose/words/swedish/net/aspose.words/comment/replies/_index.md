---
title: Comment.Replies
second_title: Aspose.Words för .NET API Referens
description: Comment fast egendom. Returnerar en samling avComment objekt som är omedelbara underordnade av den angivna kommentaren.
type: docs
weight: 90
url: /sv/net/aspose.words/comment/replies/
---
## Comment.Replies property

Returnerar en samling av[`Comment`](../) objekt som är omedelbara underordnade av den angivna kommentaren.

```csharp
public CommentCollection Replies { get; }
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

* class [CommentCollection](../../commentcollection/)
* class [Comment](../)
* namnutrymme [Aspose.Words](../../comment/)
* hopsättning [Aspose.Words](../../../)


