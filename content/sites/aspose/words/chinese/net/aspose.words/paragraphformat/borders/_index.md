---
title: ParagraphFormat.Borders
second_title: Aspose.Words for .NET API 参考
description: ParagraphFormat 财产. 获取段落边框的集合
type: docs
weight: 50
url: /zh/net/aspose.words/paragraphformat/borders/
---
## ParagraphFormat.Borders property

获取段落边框的集合。

```csharp
public BorderCollection Borders { get; }
```

### 例子

演示如何插入带有上边框的段落。

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

### 也可以看看

* class [BorderCollection](../../bordercollection/)
* class [ParagraphFormat](../)
* 命名空间 [Aspose.Words](../../paragraphformat/)
* 部件 [Aspose.Words](../../../)


