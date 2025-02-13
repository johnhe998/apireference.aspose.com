---
title: Story.AppendParagraph
second_title: Référence de l'API Aspose.Words pour .NET
description: Story méthode. Une méthode de raccourci qui crée unParagraph objet avec du texte facultatif et lajoute à la fin de cet objet.
type: docs
weight: 60
url: /fr/net/aspose.words/story/appendparagraph/
---
## Story.AppendParagraph method

Une méthode de raccourci qui crée un[`Paragraph`](../../paragraph/) objet avec du texte facultatif et l'ajoute à la fin de cet objet.

```csharp
public Paragraph AppendParagraph(string text)
```

| Paramètre | Taper | La description |
| --- | --- | --- |
| text | String | Le texte du paragraphe. Peut être une chaîne nulle ou vide. |

### Return_Value

Le paragraphe nouvellement créé et ajouté.

### Exemples

Montre comment créer un en-tête et un pied de page.

```csharp
Document doc = new Document();

// Crée un en-tête et y ajoute un paragraphe. Le texte de ce paragraphe
// apparaîtra en haut de chaque page de cette section, au-dessus du corps du texte principal.
HeaderFooter header = new HeaderFooter(doc, HeaderFooterType.HeaderPrimary);
doc.FirstSection.HeadersFooters.Add(header);

Paragraph para = header.AppendParagraph("My header.");

Assert.True(header.IsHeader);
Assert.True(para.IsEndOfHeaderFooter);

// Crée un pied de page et y ajoute un paragraphe. Le texte de ce paragraphe
// apparaîtra au bas de chaque page de cette section, sous le corps du texte principal.
HeaderFooter footer = new HeaderFooter(doc, HeaderFooterType.FooterPrimary);
doc.FirstSection.HeadersFooters.Add(footer);

para = footer.AppendParagraph("My footer.");

Assert.False(footer.IsHeader);
Assert.True(para.IsEndOfHeaderFooter);

Assert.AreEqual(footer, para.ParentStory);
Assert.AreEqual(footer.ParentSection, para.ParentSection);
Assert.AreEqual(footer.ParentSection, header.ParentSection);

doc.Save(ArtifactsDir + "HeaderFooter.Create.docx");
```

### Voir également

* class [Paragraph](../../paragraph/)
* class [Story](../)
* espace de noms [Aspose.Words](../../story/)
* Assemblée [Aspose.Words](../../../)


