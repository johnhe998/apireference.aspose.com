---
title: ParagraphFormat.Shading
second_title: Référence de l'API Aspose.Words pour .NET
description: ParagraphFormat propriété. Renvoie un objet Shading qui fait référence à la mise en forme de lombrage du paragraphe.
type: docs
weight: 270
url: /fr/net/aspose.words/paragraphformat/shading/
---
## ParagraphFormat.Shading property

Renvoie un objet Shading qui fait référence à la mise en forme de l'ombrage du paragraphe.

```csharp
public Shading Shading { get; }
```

### Exemples

Montre comment décorer du texte avec des bordures et des ombres.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

BorderCollection borders = builder.ParagraphFormat.Borders;
borders.DistanceFromText = 20;
borders[BorderType.Left].LineStyle = LineStyle.Double;
borders[BorderType.Right].LineStyle = LineStyle.Double;
borders[BorderType.Top].LineStyle = LineStyle.Double;
borders[BorderType.Bottom].LineStyle = LineStyle.Double;

Shading shading = builder.ParagraphFormat.Shading;
shading.Texture = TextureIndex.TextureDiagonalCross;
shading.BackgroundPatternColor = Color.LightCoral;
shading.ForegroundPatternColor = Color.LightSalmon;

builder.Write("This paragraph is formatted with a double border and shading.");
doc.Save(ArtifactsDir + "DocumentBuilder.ApplyBordersAndShading.docx");
```

### Voir également

* class [Shading](../../shading/)
* class [ParagraphFormat](../)
* espace de noms [Aspose.Words](../../paragraphformat/)
* Assemblée [Aspose.Words](../../../)


