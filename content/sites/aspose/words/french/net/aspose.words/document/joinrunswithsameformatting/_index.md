---
title: Document.JoinRunsWithSameFormatting
second_title: Référence de l'API Aspose.Words pour .NET
description: Document méthode. Les jointures sexécutent avec le même formatage dans tous les paragraphes du document.
type: docs
weight: 600
url: /fr/net/aspose.words/document/joinrunswithsameformatting/
---
## Document.JoinRunsWithSameFormatting method

Les jointures s'exécutent avec le même formatage dans tous les paragraphes du document.

```csharp
public int JoinRunsWithSameFormatting()
```

### Return_Value

Nombre de jointures effectuées. Lorsque **N** les pistes adjacentes sont jointes, elles comptent comme **N-1** rejoint.

### Remarques

Il s'agit d'une méthode d'optimisation. Certains documents contiennent des séries adjacentes avec le même formatage. Cela se produit généralement si un document a été modifié manuellement de manière intensive. Vous pouvez réduire la taille du document et accélérer le traitement ultérieur en joignant ces séries.

L'opération vérifie chaque[`Paragraph`](../../paragraph/) nœud dans le document pour adjacent[`Run`](../../run/) nœuds ayant des propriétés identiques. Il ignore les identifiants uniques utilisés pour suivre les sessions d'édition de run création et modification. La première exécution de chaque séquence de jointure accumule tout le texte. Les exécutions restantes sont supprimées du document.

### Exemples

Montre comment joindre des exécutions dans un document pour réduire les exécutions inutiles.

```csharp
// Ouvre un document contenant des passages de texte adjacents avec une mise en forme identique,
// qui se produit généralement si nous modifions le même paragraphe plusieurs fois dans Microsoft Word.
Document doc = new Document(MyDir + "Rendering.docx");

// Si un certain nombre de ces exécutions sont adjacentes avec un formatage identique,
// alors le document peut être simplifié.
Assert.AreEqual(317, doc.GetChildNodes(NodeType.Run, true).Count);

// Combinez ces exécutions avec cette méthode et vérifiez le nombre de jointures d'exécution qui auront lieu.
Assert.AreEqual(121, doc.JoinRunsWithSameFormatting());

// Le nombre de jointures et le nombre d'exécutions que nous avons après la jointure
// devrait additionner le nombre d'exécutions que nous avions initialement.
Assert.AreEqual(196, doc.GetChildNodes(NodeType.Run, true).Count);
```

### Voir également

* class [Document](../)
* espace de noms [Aspose.Words](../../document/)
* Assemblée [Aspose.Words](../../../)


