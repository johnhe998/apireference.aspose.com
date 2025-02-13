---
title: InlineStory.IsMoveToRevision
second_title: Référence de l'API Aspose.Words pour .NET
description: InlineStory propriété. Retours vrai si cet objet a été déplacé inséré dans Microsoft Word alors que le suivi des modifications était activé.
type: docs
weight: 60
url: /fr/net/aspose.words/inlinestory/ismovetorevision/
---
## InlineStory.IsMoveToRevision property

Retours **vrai** si cet objet a été déplacé (inséré) dans Microsoft Word alors que le suivi des modifications était activé.

```csharp
public bool IsMoveToRevision { get; }
```

### Exemples

Montre comment afficher les propriétés liées à la révision des nœuds InlineStory.

```csharp
Document doc = new Document(MyDir + "Revision footnotes.docx");

// Lorsque nous modifions le document alors que l'option "Suivre les modifications", trouvée dans via Révision -> Suivi,
// est activé dans Microsoft Word, les modifications que nous appliquons comptent comme des révisions.
// Lors de l'édition d'un document à l'aide de Aspose.Words, nous pouvons commencer à suivre les révisions en
// appelant la méthode "StartTrackRevisions" du document et arrêtant le suivi en utilisant la méthode "StopTrackRevisions".
// On peut soit accepter des révisions pour les assimiler dans le document
// ou rejetez-les pour annuler et supprimer la modification proposée.
Assert.IsTrue(doc.HasRevisions);

List<Footnote> footnotes = doc.GetChildNodes(NodeType.Footnote, true).Cast<Footnote>().ToList();

Assert.AreEqual(5, footnotes.Count);

// Vous trouverez ci-dessous cinq types de révisions pouvant signaler un nœud InlineStory.
// 1 - Une révision "insert":
// Cette révision se produit lorsque nous insérons du texte lors du suivi des modifications.
Assert.IsTrue(footnotes[2].IsInsertRevision);

// 2 - Une révision "déplacer de" :
// Lorsque nous mettons en surbrillance du texte dans Microsoft Word, puis le faisons glisser vers un autre endroit du document
// lors du suivi des modifications, deux révisions apparaissent.
// La révision "move from" est une copie du texte d'origine avant que nous ne le déplacions.
Assert.IsTrue(footnotes[4].IsMoveFromRevision);

// 3 - Une révision "déplacer vers" :
// La révision "move to" est le texte que nous avons déplacé dans sa nouvelle position dans le document.
// Les révisions "Move from" et "move to" apparaissent par paires pour chaque révision de déplacement que nous effectuons.
// Accepter une révision de déplacement supprime la révision "déplacer de" et son texte,
// et conserve le texte de la révision "déplacer vers".
// Le rejet d'une révision de déplacement conserve à l'inverse la révision "déplacer de" et supprime la révision "déplacer vers".
Assert.IsTrue(footnotes[1].IsMoveToRevision);

// 4 - Une révision "supprimer":
// Cette révision se produit lorsque nous supprimons du texte lors du suivi des modifications. Lorsque nous supprimons un texte comme celui-ci,
// il restera dans le document en tant que révision jusqu'à ce que nous acceptions la révision,
// qui supprimera définitivement le texte ou rejettera la révision, ce qui conservera le texte que nous avons supprimé là où il se trouvait.
Assert.IsTrue(footnotes[3].IsDeleteRevision);
```

### Voir également

* class [InlineStory](../)
* espace de noms [Aspose.Words](../../inlinestory/)
* Assemblée [Aspose.Words](../../../)


