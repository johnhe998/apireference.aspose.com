---
title: ParagraphFormat.Borders
second_title: Référence de l'API Aspose.Words pour .NET
description: ParagraphFormat propriété. Obtient la collection de bordures du paragraphe.
type: docs
weight: 50
url: /fr/net/aspose.words/paragraphformat/borders/
---
## ParagraphFormat.Borders property

Obtient la collection de bordures du paragraphe.

```csharp
public BorderCollection Borders { get; }
```

### Exemples

Montre comment insérer un paragraphe avec une bordure supérieure.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Border topBorder = builder.ParagraphFormat.Borders[BorderType.Top];
topBorder.Color = Color.Red;
topBorder.LineWidth = 4.0d;
topBorder.LineStyle = LineStyle.DashSmallGap;

builder.Writeln("Text with a red top border.");

doc.Save(ArtifactsDir + "Border.ParagraphTopBorder.docx");
```

### Voir également

* class [BorderCollection](../../bordercollection/)
* class [ParagraphFormat](../)
* espace de noms [Aspose.Words](../../paragraphformat/)
* Assemblée [Aspose.Words](../../../)


