---
title: FrameFormat.HorizontalAlignment
second_title: Справочник по API Aspose.Words для .NET
description: FrameFormat свойство. Получает горизонтальное выравнивание указанного кадра.
type: docs
weight: 30
url: /ru/net/aspose.words/frameformat/horizontalalignment/
---
## FrameFormat.HorizontalAlignment property

Получает горизонтальное выравнивание указанного кадра.

```csharp
public HorizontalAlignment HorizontalAlignment { get; }
```

### Примеры

Показывает, как получить информацию о свойствах форматирования абзацев, являющихся фреймами.

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

### Смотрите также

* enum [HorizontalAlignment](../../../aspose.words.drawing/horizontalalignment/)
* class [FrameFormat](../)
* пространство имен [Aspose.Words](../../frameformat/)
* сборка [Aspose.Words](../../../)


