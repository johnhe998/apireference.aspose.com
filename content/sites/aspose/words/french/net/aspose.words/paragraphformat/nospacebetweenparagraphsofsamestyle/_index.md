---
title: ParagraphFormat.NoSpaceBetweenParagraphsOfSameStyle
second_title: Référence de l'API Aspose.Words pour .NET
description: ParagraphFormat propriété. Lorsque vraiSpaceBefore etSpaceAfter sera ignoré entre les paragraphes du même style.
type: docs
weight: 230
url: /fr/net/aspose.words/paragraphformat/nospacebetweenparagraphsofsamestyle/
---
## ParagraphFormat.NoSpaceBetweenParagraphsOfSameStyle property

Lorsque vrai,[`SpaceBefore`](../spacebefore/) et[`SpaceAfter`](../spaceafter/) sera ignoré entre les paragraphes du même style.

```csharp
public bool NoSpaceBetweenParagraphsOfSameStyle { get; set; }
```

### Remarques

Ce paramètre ne prend effet que lorsqu'il est appliqué à un style de paragraphe. S'il est appliqué directement à un paragraphe, il n'a aucun effet.

### Exemples

Montre comment appliquer aucun espacement entre les paragraphes avec le même style.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Appliquez une grande quantité d'espacement avant et après les paragraphes que ce constructeur va créer.
builder.ParagraphFormat.SpaceBefore = 24;
builder.ParagraphFormat.SpaceAfter = 24;

// Définissez le drapeau "NoSpaceBetweenParagraphsOfSameStyle" sur "true" pour appliquer
// pas d'espacement entre les paragraphes de même style, ce qui regroupera les paragraphes similaires.
// Laisse le drapeau "NoSpaceBetweenParagraphsOfSameStyle" sur "false"
// pour appliquer uniformément l'espacement à chaque paragraphe.
builder.ParagraphFormat.NoSpaceBetweenParagraphsOfSameStyle = noSpaceBetweenParagraphsOfSameStyle;

builder.ParagraphFormat.Style = doc.Styles["Normal"];
builder.Writeln($"Paragraph in the \"{builder.ParagraphFormat.Style.Name}\" style.");
builder.Writeln($"Paragraph in the \"{builder.ParagraphFormat.Style.Name}\" style.");
builder.Writeln($"Paragraph in the \"{builder.ParagraphFormat.Style.Name}\" style.");
builder.ParagraphFormat.Style = doc.Styles["Quote"];
builder.Writeln($"Paragraph in the \"{builder.ParagraphFormat.Style.Name}\" style.");
builder.Writeln($"Paragraph in the \"{builder.ParagraphFormat.Style.Name}\" style.");
builder.ParagraphFormat.Style = doc.Styles["Normal"];
builder.Writeln($"Paragraph in the \"{builder.ParagraphFormat.Style.Name}\" style.");
builder.Writeln($"Paragraph in the \"{builder.ParagraphFormat.Style.Name}\" style.");

doc.Save(ArtifactsDir + "ParagraphFormat.ParagraphSpacingSameStyle.docx");
```

### Voir également

* class [ParagraphFormat](../)
* espace de noms [Aspose.Words](../../paragraphformat/)
* Assemblée [Aspose.Words](../../../)


