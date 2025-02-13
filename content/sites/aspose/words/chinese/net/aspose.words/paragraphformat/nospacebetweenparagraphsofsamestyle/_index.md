---
title: ParagraphFormat.NoSpaceBetweenParagraphsOfSameStyle
second_title: Aspose.Words for .NET API 参考
description: ParagraphFormat 财产. 为真时SpaceBefore和SpaceAfter将在相同样式的段落之间忽略 
type: docs
weight: 230
url: /zh/net/aspose.words/paragraphformat/nospacebetweenparagraphsofsamestyle/
---
## ParagraphFormat.NoSpaceBetweenParagraphsOfSameStyle property

为真时，[`SpaceBefore`](../spacebefore/)和[`SpaceAfter`](../spaceafter/)将在相同样式的段落之间忽略 。

```csharp
public bool NoSpaceBetweenParagraphsOfSameStyle { get; set; }
```

### 评论

此设置仅在应用于段落样式时生效。如果直接应用于 一个段落，是没有效果的。

### 例子

演示如何在具有相同样式的段落之间应用无间距。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 在此构建器将创建的段落之前和之后应用大量间距。
builder.ParagraphFormat.SpaceBefore = 24;
builder.ParagraphFormat.SpaceAfter = 24;

// 将“NoSpaceBetweenParagraphsOfSameStyle”标志设置为“true”以应用
// 相同样式的段落之间没有间距，这会将相似的段落分组。
// 将“NoSpaceBetweenParagraphsOfSameStyle”标志保留为“false”
// 将间距均匀地应用于每个段落。
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

### 也可以看看

* class [ParagraphFormat](../)
* 命名空间 [Aspose.Words](../../paragraphformat/)
* 部件 [Aspose.Words](../../../)


