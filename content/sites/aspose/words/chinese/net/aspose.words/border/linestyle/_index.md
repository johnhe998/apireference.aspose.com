---
title: Border.LineStyle
second_title: Aspose.Words for .NET API 参考
description: Border 财产. 获取或设置边框样式
type: docs
weight: 40
url: /zh/net/aspose.words/border/linestyle/
---
## Border.LineStyle property

获取或设置边框样式

```csharp
public LineStyle LineStyle { get; set; }
```

### 评论

如果将线型设置为无，则线宽会自动更改为零。

### 例子

演示如何将由边框包围的字符串插入到文档中。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Border.Color = Color.Green;
builder.Font.Border.LineWidth = 2.5d;
builder.Font.Border.LineStyle = LineStyle.DashDotStroker;

builder.Write("Text surrounded by green border.");

doc.Save(ArtifactsDir + "Border.FontBorder.docx");
```

### 也可以看看

* enum [LineStyle](../../linestyle/)
* class [Border](../)
* 命名空间 [Aspose.Words](../../border/)
* 部件 [Aspose.Words](../../../)


