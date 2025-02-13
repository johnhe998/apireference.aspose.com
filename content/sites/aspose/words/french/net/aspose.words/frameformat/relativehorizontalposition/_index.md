---
title: FrameFormat.RelativeHorizontalPosition
second_title: Référence de l'API Aspose.Words pour .NET
description: FrameFormat propriété. Obtient la position horizontale relative dun cadre.
type: docs
weight: 70
url: /fr/net/aspose.words/frameformat/relativehorizontalposition/
---
## FrameFormat.RelativeHorizontalPosition property

Obtient la position horizontale relative d'un cadre.

```csharp
public RelativeHorizontalPosition RelativeHorizontalPosition { get; }
```

### Exemples

Montre comment obtenir des informations sur les propriétés de mise en forme des paragraphes qui sont des cadres.

```csharp
Document doc = new Document(MyDir + "Paragraph frame.docx");

Paragraph paragraphFrame = doc.FirstSection.Body.Paragraphs.OfType<Paragraph>().First(p => p.FrameFormat.IsFrame);

Assert.AreEqual(233.3d, paragraphFrame.FrameFormat.Width);
Assert.AreEqual(138.8d, paragraphFrame.FrameFormat.Height);
Assert.AreEqual(HeightRule.AtLeast, paragraphFrame.FrameFormat.HeightRule);
Assert.AreEqual(HorizontalAlignment.Default, paragraphFrame.FrameFormat.HorizontalAlignment);
Assert.AreEqual(VerticalAlignment.Default, paragraphFrame.FrameFormat.VerticalAlignment);
Assert.AreEqual(34.05d, paragraphFrame.FrameFormat.HorizontalPosition);
Assert.AreEqual(RelativeHorizontalPosition.Page, paragraphFrame.FrameFormat.RelativeHorizontalPosition);
Assert.AreEqual(9.0d, paragraphFrame.FrameFormat.HorizontalDistanceFromText);
Assert.AreEqual(20.5d, paragraphFrame.FrameFormat.VerticalPosition);
Assert.AreEqual(RelativeVerticalPosition.Paragraph, paragraphFrame.FrameFormat.RelativeVerticalPosition);
Assert.AreEqual(0.0d, paragraphFrame.FrameFormat.VerticalDistanceFromText);
```

### Voir également

* enum [RelativeHorizontalPosition](../../../aspose.words.drawing/relativehorizontalposition/)
* class [FrameFormat](../)
* espace de noms [Aspose.Words](../../frameformat/)
* Assemblée [Aspose.Words](../../../)


