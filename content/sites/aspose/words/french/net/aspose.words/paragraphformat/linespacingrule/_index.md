---
title: ParagraphFormat.LineSpacingRule
second_title: Référence de l'API Aspose.Words pour .NET
description: ParagraphFormat propriété. Obtient ou définit linterligne du paragraphe.
type: docs
weight: 190
url: /fr/net/aspose.words/paragraphformat/linespacingrule/
---
## ParagraphFormat.LineSpacingRule property

Obtient ou définit l'interligne du paragraphe.

```csharp
public LineSpacingRule LineSpacingRule { get; set; }
```

### Exemples

Montre comment travailler avec l'interligne.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Vous trouverez ci-dessous trois règles d'interligne que nous pouvons définir à l'aide de la
// propriété "LineSpacingRule" du paragraphe pour configurer l'espacement entre les paragraphes.
// 1 - Définir un espacement minimum.
// Cela donnera un remplissage vertical aux lignes de texte de n'importe quelle taille
// qui est trop petit pour maintenir la hauteur de ligne minimale.
builder.ParagraphFormat.LineSpacingRule = LineSpacingRule.AtLeast;
builder.ParagraphFormat.LineSpacing = 20;

builder.Writeln("Minimum line spacing of 20.");
builder.Writeln("Minimum line spacing of 20.");

// 2 - Définir l'espacement exact.
// L'utilisation de tailles de police trop grandes pour l'espacement tronquera le texte.
builder.ParagraphFormat.LineSpacingRule = LineSpacingRule.Exactly;
builder.ParagraphFormat.LineSpacing = 5;

builder.Writeln("Line spacing of exactly 5.");
builder.Writeln("Line spacing of exactly 5.");

// 3 - Définissez l'espacement comme un multiple de l'espacement des lignes par défaut, qui est de 12 points par défaut.
// Ce type d'espacement s'adaptera à différentes tailles de police.
builder.ParagraphFormat.LineSpacingRule = LineSpacingRule.Multiple;
builder.ParagraphFormat.LineSpacing = 18;

builder.Writeln("Line spacing of 1.5 default lines.");
builder.Writeln("Line spacing of 1.5 default lines.");

doc.Save(ArtifactsDir + "ParagraphFormat.LineSpacing.docx");
```

### Voir également

* enum [LineSpacingRule](../../linespacingrule/)
* class [ParagraphFormat](../)
* espace de noms [Aspose.Words](../../paragraphformat/)
* Assemblée [Aspose.Words](../../../)


