---
title: Comment.Ancestor
second_title: Référence de l'API Aspose.Words pour .NET
description: Comment propriété. Renvoie lobjet Commentaire parent. Renvoie null pour les commentaires de niveau supérieur.
type: docs
weight: 20
url: /fr/net/aspose.words/comment/ancestor/
---
## Comment.Ancestor property

Renvoie l'objet Commentaire parent. Renvoie null pour les commentaires de niveau supérieur.

```csharp
public Comment Ancestor { get; }
```

### Exemples

Montre comment imprimer tous les commentaires d'un document et leurs réponses.

```csharp
Document doc = new Document(MyDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);

// Si un commentaire n'a pas d'ancêtre, il s'agit d'un commentaire "de niveau supérieur" par opposition à un commentaire de type réponse.
// Affiche tous les commentaires de haut niveau avec toutes les réponses qu'ils peuvent avoir.
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

### Voir également

* class [Comment](../)
* espace de noms [Aspose.Words](../../comment/)
* Assemblée [Aspose.Words](../../../)


