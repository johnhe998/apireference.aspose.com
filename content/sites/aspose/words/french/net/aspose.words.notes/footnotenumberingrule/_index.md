---
title: Enum FootnoteNumberingRule
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.Notes.FootnoteNumberingRule énumération. Détermine quand la numérotation automatique des notes de bas de page ou des notes de fin redémarre.
type: docs
weight: 4030
url: /fr/net/aspose.words.notes/footnotenumberingrule/
---
## FootnoteNumberingRule enumeration

Détermine quand la numérotation automatique des notes de bas de page ou des notes de fin redémarre.

```csharp
public enum FootnoteNumberingRule
```

### Valeurs

| Nom | Évaluer | La description |
| --- | --- | --- |
| Continuous | `0` | Numérotation continue dans tout le document. |
| RestartSection | `1` | La numérotation recommence à chaque section. |
| RestartPage | `2` | La numérotation recommence à chaque page. Valable uniquement pour les notes de bas de page. |
| Default | `0` | est égal àContinuous . |

### Exemples

Montre comment redémarrer la numérotation des notes de bas de page/notes de fin à certains endroits du document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Les notes de bas de page et les notes de fin sont un moyen d'attacher une référence ou un commentaire latéral au texte
// qui n'interfère pas avec le flux du corps du texte principal. 
// L'insertion d'une note de bas de page/note de fin ajoute un petit symbole de référence en exposant
// au corps du texte principal où nous insérons la note de bas de page/note de fin.
// Chaque note de bas de page/note de fin crée également une entrée, qui consiste en un symbole correspondant à la référence
// symbole dans le corps du texte principal. Le texte de référence que nous transmettons à la méthode "InsertEndnote" du générateur de document.
// Les entrées de note de bas de page, par défaut, s'affichent au bas de chaque page contenant
// leurs symboles de référence et les notes de fin apparaissent à la fin du document.
builder.Write("Text 1. ");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote 1.");
builder.Write("Text 2. ");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote 2.");
builder.InsertBreak(BreakType.PageBreak);
builder.Write("Text 3. ");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote 3.");
builder.Write("Text 4. ");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote 4.");

builder.InsertBreak(BreakType.PageBreak);

builder.Write("Text 1. ");
builder.InsertFootnote(FootnoteType.Endnote, "Endnote 1.");
builder.Write("Text 2. ");
builder.InsertFootnote(FootnoteType.Endnote, "Endnote 2.");
builder.InsertBreak(BreakType.SectionBreakNewPage);
builder.Write("Text 3. ");
builder.InsertFootnote(FootnoteType.Endnote, "Endnote 3.");
builder.Write("Text 4. ");
builder.InsertFootnote(FootnoteType.Endnote, "Endnote 4.");

// Par défaut, le symbole de référence pour chaque note de bas de page et note de fin est son index
// parmi toutes les notes de bas de page/notes de fin du document. Chaque document maintient des comptes séparés
// pour les notes de bas de page et les notes de fin et ne redémarre à aucun moment ces décomptes.
Assert.AreEqual(doc.FootnoteOptions.RestartRule, FootnoteNumberingRule.Default);
Assert.AreEqual(FootnoteNumberingRule.Default, FootnoteNumberingRule.Continuous);

// Nous pouvons utiliser la propriété "RestartRule" pour faire redémarrer le document
// la note de bas de page/note de fin compte à une nouvelle page ou section.
doc.FootnoteOptions.RestartRule = FootnoteNumberingRule.RestartPage;
doc.EndnoteOptions.RestartRule = FootnoteNumberingRule.RestartSection;

doc.Save(ArtifactsDir + "InlineStory.NumberingRule.docx");
```

### Voir également

* class [FootnoteOptions](../footnoteoptions/)
* class [EndnoteOptions](../endnoteoptions/)
* espace de noms [Aspose.Words.Notes](../../aspose.words.notes/)
* Assemblée [Aspose.Words](../../)


