---
title: Footnote.Footnote
second_title: Référence de l'API Aspose.Words pour .NET
description: Footnote constructeur. Initialise une instance du note de bas de page classe.
type: docs
weight: 10
url: /fr/net/aspose.words.notes/footnote/footnote/
---
## Footnote constructor

Initialise une instance du **note de bas de page** classe.

```csharp
public Footnote(DocumentBase doc, FootnoteType footnoteType)
```

| Paramètre | Taper | La description |
| --- | --- | --- |
| doc | DocumentBase | Le document du propriétaire. |
| footnoteType | FootnoteType | UN[`FootnoteType`](../footnotetype/) value qui spécifie s'il s'agit d'une note de bas de page ou d'une note de fin. |

### Remarques

Lorsque **note de bas de page** est créé, il appartient au document spécifié, mais ne fait pas encore partie du document et **ParentNode** est nul.

À ajouter **note de bas de page** au document, utilisez InsertAfter ou InsertBefore sur le paragraphe où vous souhaitez insérer la note de bas de page.

### Exemples

Montre comment insérer et personnaliser des notes de bas de page.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Ajoutez du texte et référencez-le avec une note de bas de page. Cette note de bas de page placera une petite référence en exposant
// marquer après le texte auquel il fait référence et créer une entrée sous le corps du texte principal au bas de la page.
// Cette entrée contiendra la marque de référence de la note de bas de page et le texte de référence,
// que nous transmettrons à la méthode "InsertFootnote" du générateur de document.
builder.Write("Main body text.");
Footnote footnote = builder.InsertFootnote(FootnoteType.Footnote, "Footnote text.");

// Si cette propriété vaut "true", alors le repère de notre note de bas de page
// sera son index parmi toutes les notes de bas de page de la section.
// Ceci est la première note de bas de page, donc la marque de référence sera "1".
Assert.True(footnote.IsAuto);

// Nous pouvons déplacer le générateur de document à l'intérieur de la note de bas de page pour modifier son texte de référence. 
builder.MoveTo(footnote.FirstParagraph);
builder.Write(" More text added by a DocumentBuilder.");
builder.MoveToDocumentEnd();

Assert.AreEqual("\u0002 Footnote text. More text added by a DocumentBuilder.", footnote.GetText().Trim());

builder.Write(" More main body text.");
footnote = builder.InsertFootnote(FootnoteType.Footnote, "Footnote text.");

// Nous pouvons définir une marque de référence personnalisée que la note de bas de page utilisera à la place de son numéro d'index.
footnote.ReferenceMark = "RefMark";

Assert.False(footnote.IsAuto);

// Un signet avec le drapeau "IsAuto" défini sur true affichera toujours son index réel
// même si les signets précédents affichent des marques de référence personnalisées, la marque de référence de ce signet sera donc un "3".
builder.Write(" More main body text.");
footnote = builder.InsertFootnote(FootnoteType.Footnote, "Footnote text.");

Assert.True(footnote.IsAuto);

doc.Save(ArtifactsDir + "InlineStory.AddFootnote.docx");
```

### Voir également

* class [DocumentBase](../../../aspose.words/documentbase/)
* enum [FootnoteType](../../footnotetype/)
* class [Footnote](../)
* espace de noms [Aspose.Words.Notes](../../footnote/)
* Assemblée [Aspose.Words](../../../)


