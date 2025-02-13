---
title: HeaderFooter.HeaderFooter
second_title: Référence de l'API Aspose.Words pour .NET
description: HeaderFooter constructeur. Crée un nouvel entête ou pied de page du type spécifié.
type: docs
weight: 10
url: /fr/net/aspose.words/headerfooter/headerfooter/
---
## HeaderFooter constructor

Crée un nouvel en-tête ou pied de page du type spécifié.

```csharp
public HeaderFooter(DocumentBase doc, HeaderFooterType headerFooterType)
```

| Paramètre | Taper | La description |
| --- | --- | --- |
| doc | DocumentBase | Le document du propriétaire. |
| headerFooterType | HeaderFooterType | UN[`HeaderFooterType`](../headerfootertype/)value qui spécifie le type d'en-tête ou de pied de page. |

### Remarques

Lorsque **En-têtePied de page** est créé, il appartient au document spécifié, mais ne fait pas encore partie du document et **ParentNode** est nul.

À ajouter **En-têtePied de page** à un **Section** utilisez Section.InsertAfter, Section.InsertBefore, HeadersFooters.Add ou HeadersFooters.Insert.

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

* class [DocumentBase](../../documentbase/)
* enum [HeaderFooterType](../../headerfootertype/)
* class [HeaderFooter](../)
* espace de noms [Aspose.Words](../../headerfooter/)
* Assemblée [Aspose.Words](../../../)


