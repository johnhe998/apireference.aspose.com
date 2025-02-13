---
title: Node.Clone
second_title: Référence de l'API Aspose.Words pour .NET
description: Node méthode. Crée un doublon du nœud.
type: docs
weight: 100
url: /fr/net/aspose.words/node/clone/
---
## Node.Clone method

Crée un doublon du nœud.

```csharp
public Node Clone(bool isCloneChildren)
```

| Paramètre | Taper | La description |
| --- | --- | --- |
| isCloneChildren | Boolean | True pour cloner récursivement la sous-arborescence sous le nœud spécifié ; false pour cloner uniquement le nœud lui-même. |

### Return_Value

Le nœud cloné.

### Remarques

Cette méthode sert de constructeur de copie pour les nœuds. Le nœud cloné n'a pas de parent, mais appartient au même document que le nœud d'origine.

Cette méthode effectue toujours une copie complète du nœud. LaisCloneChildren parameter spécifie s'il faut également copier tous les nœuds enfants.

### Exemples

Montre comment cloner un nœud composite.

```csharp
Document doc = new Document();
Paragraph para = doc.FirstSection.Body.FirstParagraph;
para.AppendChild(new Run(doc, "Hello world!"));

// Vous trouverez ci-dessous deux manières de cloner un nœud composite.
// 1 - Crée un clone d'un nœud et crée également un clone de chacun de ses nœuds enfants.
Node cloneWithChildren = para.Clone(true);

Assert.IsTrue(((CompositeNode)cloneWithChildren).HasChildNodes);
Assert.AreEqual("Hello world!", cloneWithChildren.GetText().Trim());

// 2 - Créer un clone d'un nœud tout seul sans aucun enfant.
Node cloneWithoutChildren = para.Clone(false);

Assert.IsFalse(((CompositeNode)cloneWithoutChildren).HasChildNodes);
Assert.AreEqual(string.Empty, cloneWithoutChildren.GetText().Trim());
```

### Voir également

* class [Node](../)
* espace de noms [Aspose.Words](../../node/)
* Assemblée [Aspose.Words](../../../)


