---
title: Enum FootnoteType
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.Notes.FootnoteType énumération. Spécifie sil sagit dune note de bas de page ou dune note de fin.
type: docs
weight: 4060
url: /fr/net/aspose.words.notes/footnotetype/
---
## FootnoteType enumeration

Spécifie s'il s'agit d'une note de bas de page ou d'une note de fin.

```csharp
public enum FootnoteType
```

### Valeurs

| Nom | Évaluer | La description |
| --- | --- | --- |
| Footnote | `0` | L'objet est une note de bas de page. |
| Endnote | `1` | L'objet est une note de fin. |

### Remarques

Les notes de bas de page et les notes de fin sont représentées par des objets par leFootnote classe. Utilisation[`FootnoteType`](../footnote/footnotetype/) pour faire la distinction entre les notes de bas de page et les notes de fin.

### Exemples

Montre comment référencer du texte avec une note de bas de page et une note de fin.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insérez du texte et marquez-le d'une note de bas de page avec la propriété IsAuto définie sur "true" par défaut,
// donc le marqueur vu dans le corps du texte sera numéroté automatiquement à "1",
// et la note de bas de page apparaîtra en bas de la page.
builder.Write("This text will be referenced by a footnote.");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote comment regarding referenced text.");

// Insérer plus de texte et le marquer avec une note de fin avec une marque de référence personnalisée,
// qui sera utilisé à la place du nombre "2" et définira "IsAuto" sur false.
builder.Write("This text will be referenced by an endnote.");
builder.InsertFootnote(FootnoteType.Endnote, "Endnote comment regarding referenced text.", "CustomMark");

// Les notes de bas de page apparaissent toujours en bas de leur texte référencé,
// donc ce saut de page n'affectera pas la note de bas de page.
// Par contre, les notes de fin sont toujours à la fin du document
// pour que ce saut de page pousse la note de fin à la page suivante.
builder.InsertBreak(BreakType.PageBreak);

doc.Save(ArtifactsDir + "DocumentBuilder.InsertFootnote.docx");
```

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

* espace de noms [Aspose.Words.Notes](../../aspose.words.notes/)
* Assemblée [Aspose.Words](../../)


