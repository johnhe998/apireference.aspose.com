---
title: Paragraph.BreakIsStyleSeparator
second_title: Référence de l'API Aspose.Words pour .NET
description: Paragraph propriété. Vrai si ce saut de paragraphe est un séparateur de style. Un séparateur de style permet à un paragraphe de se composer de parties qui ont différents styles de paragraphe.
type: docs
weight: 20
url: /fr/net/aspose.words/paragraph/breakisstyleseparator/
---
## Paragraph.BreakIsStyleSeparator property

Vrai si ce saut de paragraphe est un séparateur de style. Un séparateur de style permet à un paragraphe de se composer de parties qui ont différents styles de paragraphe.

```csharp
public bool BreakIsStyleSeparator { get; }
```

### Exemples

Montre comment écrire du texte sur la même ligne qu'un titre de table des matières et ne pas l'afficher dans la table des matières.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertTableOfContents("\\o \\h \\z \\u");
builder.InsertBreak(BreakType.PageBreak);

// Insère un paragraphe avec un style que la table des matières reprendra comme entrée.
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

// Ces deux chaînes se trouvent dans le même paragraphe et apparaîtront donc sur la même entrée de table des matières.
builder.Write("Heading 1. ");
builder.Write("Will appear in the TOC. ");

// Si nous insérons un séparateur de style, nous pouvons écrire plus de texte dans le même paragraphe
// et utiliser un style différent sans apparaître dans la table des matières.
// Si nous utilisons un style de type de titre après le séparateur, nous pouvons dessiner plusieurs entrées de table des matières à partir d'une ligne de texte de document.
builder.InsertStyleSeparator();
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Quote;
builder.Write("Won't appear in the TOC. ");

Assert.True(doc.FirstSection.Body.FirstParagraph.BreakIsStyleSeparator);

doc.UpdateFields();
doc.Save(ArtifactsDir + "Paragraph.BreakIsStyleSeparator.docx");
```

### Voir également

* class [Paragraph](../)
* espace de noms [Aspose.Words](../../paragraph/)
* Assemblée [Aspose.Words](../../../)


