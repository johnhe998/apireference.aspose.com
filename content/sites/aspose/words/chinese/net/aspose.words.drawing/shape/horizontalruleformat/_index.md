---
title: Shape.HorizontalRuleFormat
second_title: Aspose.Words for .NET API 参考
description: Shape 财产. 提供对水平规则形状属性的访问 对于不是水平规则的形状返回 null
type: docs
weight: 100
url: /zh/net/aspose.words.drawing/shape/horizontalruleformat/
---
## Shape.HorizontalRuleFormat property

提供对水平规则形状属性的访问。 对于不是水平规则的形状，返回 null。

```csharp
public HorizontalRuleFormat HorizontalRuleFormat { get; }
```

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

* class [HorizontalRuleFormat](../../horizontalruleformat/)
* class [Shape](../)
* 命名空间 [Aspose.Words.Drawing](../../shape/)
* 部件 [Aspose.Words](../../../)


