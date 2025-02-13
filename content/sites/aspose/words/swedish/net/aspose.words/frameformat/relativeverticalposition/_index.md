---
title: FrameFormat.RelativeVerticalPosition
second_title: Aspose.Words för .NET API Referens
description: FrameFormat fast egendom. Får den relativa vertikala positionen för en ram.
type: docs
weight: 80
url: /sv/net/aspose.words/frameformat/relativeverticalposition/
---
## FrameFormat.RelativeVerticalPosition property

Får den relativa vertikala positionen för en ram.

```csharp
public RelativeVerticalPosition RelativeVerticalPosition { get; }
```

### Exempel

Visar hur man får information om formateringsegenskaper för stycken som är ramar.

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

### Se även

* enum [RelativeVerticalPosition](../../../aspose.words.drawing/relativeverticalposition/)
* class [FrameFormat](../)
* namnutrymme [Aspose.Words](../../frameformat/)
* hopsättning [Aspose.Words](../../../)


