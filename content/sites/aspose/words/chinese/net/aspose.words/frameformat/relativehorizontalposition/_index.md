---
title: FrameFormat.RelativeHorizontalPosition
second_title: Aspose.Words for .NET API 参考
description: FrameFormat 财产. 获取帧的相对水平位置
type: docs
weight: 70
url: /zh/net/aspose.words/frameformat/relativehorizontalposition/
---
## FrameFormat.RelativeHorizontalPosition property

获取帧的相对水平位置。

```csharp
public RelativeHorizontalPosition RelativeHorizontalPosition { get; }
```

### 例子

显示如何获取有关作为框架的段落的格式属性的信息。

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

### 也可以看看

* enum [RelativeHorizontalPosition](../../../aspose.words.drawing/relativehorizontalposition/)
* class [FrameFormat](../)
* 命名空间 [Aspose.Words](../../frameformat/)
* 部件 [Aspose.Words](../../../)


