---
title: Paragraph.GetEffectiveTabStops
second_title: Référence de l'API Aspose.Words pour .NET
description: Paragraph méthode. Renvoie un tableau de tous les taquets de tabulation appliqués à ce paragraphe y compris appliqués indirectement par des styles ou des listes.
type: docs
weight: 250
url: /fr/net/aspose.words/paragraph/geteffectivetabstops/
---
## Paragraph.GetEffectiveTabStops method

Renvoie un tableau de tous les taquets de tabulation appliqués à ce paragraphe, y compris appliqués indirectement par des styles ou des listes.

```csharp
public TabStop[] GetEffectiveTabStops()
```

### Exemples

Montre comment définir des taquets de tabulation personnalisés pour un paragraphe.

```csharp
Document doc = new Document();
Paragraph para = doc.FirstSection.Body.FirstParagraph;

// Si nous sommes dans un paragraphe sans tabulation dans cette collection,
// le curseur sautera 36 points chaque fois que nous appuierons sur la touche Tab dans Microsoft Word.
Assert.AreEqual(0, doc.FirstSection.Body.FirstParagraph.GetEffectiveTabStops().Length);

// Nous pouvons ajouter des taquets de tabulation personnalisés dans Microsoft Word si nous activons la règle via l'onglet "Affichage".
// Chaque unité de cette règle correspond à deux taquets de tabulation par défaut, soit 72 points.
// Nous pouvons ajouter des taquets de tabulation personnalisés par programmation comme ceci.
TabStopCollection tabStops = doc.FirstSection.Body.FirstParagraph.ParagraphFormat.TabStops;
tabStops.Add(72, TabAlignment.Left, TabLeader.Dots);
tabStops.Add(216, TabAlignment.Center, TabLeader.Dashes);
tabStops.Add(360, TabAlignment.Right, TabLeader.Line);

// Nous pouvons voir ces taquets de tabulation dans Microsoft Word en activant la règle via "Affichage" -> "Afficher" -> "Règle".
Assert.AreEqual(3, para.GetEffectiveTabStops().Length);

// Tous les caractères de tabulation que nous ajoutons utiliseront les taquets de tabulation sur la règle et peuvent,
// en fonction de la valeur du chef de tabulation, laisser une ligne entre les destinations de départ et d'arrivée de la tabulation.
para.AppendChild(new Run(doc, "\tTab 1\tTab 2\tTab 3"));

doc.Save(ArtifactsDir + "Paragraph.TabStops.docx");
```

### Voir également

* class [TabStop](../../tabstop/)
* class [Paragraph](../)
* espace de noms [Aspose.Words](../../paragraph/)
* Assemblée [Aspose.Words](../../../)


