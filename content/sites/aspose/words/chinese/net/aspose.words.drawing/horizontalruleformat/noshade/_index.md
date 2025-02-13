---
title: HorizontalRuleFormat.NoShade
second_title: Aspose.Words for .NET API 参考
description: HorizontalRuleFormat 财产. 表示水平标尺存在 3D 底纹 如果为真则水平标尺没有 3D 底纹并使用纯色
type: docs
weight: 40
url: /zh/net/aspose.words.drawing/horizontalruleformat/noshade/
---
## HorizontalRuleFormat.NoShade property

表示水平标尺存在 3D 底纹。 如果为真，则水平标尺没有 3D 底纹并使用纯色。

```csharp
public bool NoShade { get; set; }
```

### 评论

默认值为假。

### 例子

显示如何插入水平线形，并自定义其格式。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.InsertHorizontalRule();

HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;

Assert.True(shape.IsHorizontalRule);
Assert.True(shape.HorizontalRuleFormat.NoShade);
```

### 也可以看看

* class [HorizontalRuleFormat](../)
* 命名空间 [Aspose.Words.Drawing](../../horizontalruleformat/)
* 部件 [Aspose.Words](../../../)


