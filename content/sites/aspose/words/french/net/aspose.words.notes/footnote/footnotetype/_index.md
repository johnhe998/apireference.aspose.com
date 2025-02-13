---
title: Footnote.FootnoteType
second_title: Référence de l'API Aspose.Words pour .NET
description: Footnote propriété. Renvoie une valeur qui spécifie sil sagit dune note de bas de page ou dune note de fin.
type: docs
weight: 20
url: /fr/net/aspose.words.notes/footnote/footnotetype/
---
## Footnote.FootnoteType property

Renvoie une valeur qui spécifie s'il s'agit d'une note de bas de page ou d'une note de fin.

```csharp
public FootnoteType FootnoteType { get; }
```

### Exemples

Montre la différence entre les notes de bas de page et les notes de fin.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Vous trouverez ci-dessous deux manières d'attacher des références numérotées au texte. Ces deux références ajouteront une
// petite marque de référence en exposant à l'endroit où nous les insérons.
// La marque de référence, par défaut, est le numéro d'index de la référence parmi toutes les références du document.
// Chaque référence créera également une entrée, qui aura la même marque de référence que dans le corps du texte
// et le texte de référence, que nous transmettrons à la méthode "InsertFootnote" du générateur de documents.
// 1 - Une note de bas de page, dont l'entrée apparaîtra sur la même page que le texte auquel elle fait référence :
builder.Write("Footnote referenced main body text.");
Footnote footnote = builder.InsertFootnote(FootnoteType.Footnote, 
    "Footnote text, will appear at the bottom of the page that contains the referenced text.");

// 2 - Une note de fin, dont l'entrée apparaîtra à la fin du document :
builder.Write("Endnote referenced main body text.");
Footnote endnote = builder.InsertFootnote(FootnoteType.Endnote, 
    "Endnote text, will appear at the very end of the document.");

builder.InsertBreak(BreakType.SectionBreakNewPage);
builder.InsertBreak(BreakType.SectionBreakNewPage);

Assert.AreEqual(FootnoteType.Footnote, footnote.FootnoteType);
Assert.AreEqual(FootnoteType.Endnote, endnote.FootnoteType);

doc.Save(ArtifactsDir + "InlineStory.FootnoteEndnote.docx");
```

### Voir également

* enum [FootnoteType](../../footnotetype/)
* class [Footnote](../)
* espace de noms [Aspose.Words.Notes](../../footnote/)
* Assemblée [Aspose.Words](../../../)


