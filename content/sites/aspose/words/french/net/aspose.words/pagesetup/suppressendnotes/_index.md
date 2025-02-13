---
title: PageSetup.SuppressEndnotes
second_title: Référence de l'API Aspose.Words pour .NET
description: PageSetup propriété. Vrai si les notes de fin sont imprimées à la fin de la section suivante qui ne supprime pas les notes de fin. Les notes de fin supprimées sont imprimées avant les notes de fin de cette section.
type: docs
weight: 400
url: /fr/net/aspose.words/pagesetup/suppressendnotes/
---
## PageSetup.SuppressEndnotes property

**Vrai** si les notes de fin sont imprimées à la fin de la section suivante qui ne supprime pas les notes de fin. Les notes de fin supprimées sont imprimées avant les notes de fin de cette section.

```csharp
public bool SuppressEndnotes { get; set; }
```

### Exemples

Montre comment stocker les notes de fin à la fin de chaque section et modifier leur position.

```csharp
{
    Document doc = new Document();
    doc.RemoveAllChildren();

     // Par défaut, un document compile toutes les notes de fin à sa fin.
    Assert.AreEqual(EndnotePosition.EndOfDocument, doc.EndnoteOptions.Position);

    // On utilise la propriété "Position" de l'objet "EndnoteOptions" du document
     // pour collecter les notes de fin à la fin de chaque section à la place.
    doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;

    InsertSectionWithEndnote(doc, "Section 1", "Endnote 1, will stay in section 1");
    InsertSectionWithEndnote(doc, "Section 2", "Endnote 2, will be pushed down to section 3");
    InsertSectionWithEndnote(doc, "Section 3", "Endnote 3, will stay in section 3");

    // Lors de l'obtention des sections pour afficher leurs notes de fin respectives, nous pouvons définir le drapeau "SuppressEndnotes"
    // de l'objet "PageSetup" d'une section à "true" pour revenir au comportement par défaut et passer ses notes de fin
    // sur la section suivante.
    PageSetup pageSetup = doc.Sections[1].PageSetup;
    pageSetup.SuppressEndnotes = true;

    doc.Save(ArtifactsDir + "PageSetup.SuppressEndnotes.docx");

/// <summary>
/// Ajoute une section avec du texte et une note de fin à un document.
/// </summary>
private static void InsertSectionWithEndnote(Document doc, string sectionBodyText, string endnoteText)
{
    Section section = new Section(doc);

    doc.AppendChild(section);

    Body body = new Body(doc);
    section.AppendChild(body);

    Assert.AreEqual(section, body.ParentNode);

    Paragraph para = new Paragraph(doc);
    body.AppendChild(para);

    Assert.AreEqual(body, para.ParentNode);

    DocumentBuilder builder = new DocumentBuilder(doc);
    builder.MoveTo(para);
    builder.Write(sectionBodyText);
    builder.InsertFootnote(FootnoteType.Endnote, endnoteText);
}
```

### Voir également

* class [PageSetup](../)
* espace de noms [Aspose.Words](../../pagesetup/)
* Assemblée [Aspose.Words](../../../)


