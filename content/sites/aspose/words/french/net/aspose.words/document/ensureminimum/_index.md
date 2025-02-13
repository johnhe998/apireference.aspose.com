---
title: Document.EnsureMinimum
second_title: Référence de l'API Aspose.Words pour .NET
description: Document méthode. Si le document ne contient aucune section crée une section avec un paragraphe.
type: docs
weight: 560
url: /fr/net/aspose.words/document/ensureminimum/
---
## Document.EnsureMinimum method

Si le document ne contient aucune section, crée une section avec un paragraphe.

```csharp
public void EnsureMinimum()
```

### Exemples

Montre comment s'assurer qu'un document contient l'ensemble minimal de nœuds requis pour modifier son contenu.

```csharp
// Un document nouvellement créé contient un enfant Section, qui comprend un enfant Body et un enfant Paragraph.
// Nous pouvons modifier le contenu du corps du document en ajoutant des nœuds tels que Runs ou inline Shapes à ce paragraphe.
Document doc = new Document();
NodeCollection nodes = doc.GetChildNodes(NodeType.Any, true);

Assert.AreEqual(NodeType.Section, nodes[0].NodeType);
Assert.AreEqual(doc, nodes[0].ParentNode);

Assert.AreEqual(NodeType.Body, nodes[1].NodeType);
Assert.AreEqual(nodes[0], nodes[1].ParentNode);

Assert.AreEqual(NodeType.Paragraph, nodes[2].NodeType);
Assert.AreEqual(nodes[1], nodes[2].ParentNode);

// Il s'agit de l'ensemble minimal de nœuds dont nous avons besoin pour pouvoir modifier le document.
// Nous ne pourrons plus modifier le document si nous supprimons l'un d'entre eux.
doc.RemoveAllChildren();

Assert.AreEqual(0, doc.GetChildNodes(NodeType.Any, true).Count);

// Appelez cette méthode pour vous assurer que le document a au moins ces trois nœuds afin que nous puissions le modifier à nouveau.
doc.EnsureMinimum();

Assert.AreEqual(NodeType.Section, nodes[0].NodeType);
Assert.AreEqual(NodeType.Body, nodes[1].NodeType);
Assert.AreEqual(NodeType.Paragraph, nodes[2].NodeType);

((Paragraph)nodes[2]).Runs.Add(new Run(doc, "Hello world!"));
```

### Voir également

* class [Document](../)
* espace de noms [Aspose.Words](../../document/)
* Assemblée [Aspose.Words](../../../)


