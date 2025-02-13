---
title: HorizontalRuleFormat.Color
second_title: Aspose.Words for .NET API Referansı
description: HorizontalRuleFormat mülk. Yatay kuralı dolduran fırça rengini alır veya ayarlar.
type: docs
weight: 20
url: /tr/net/aspose.words.drawing/horizontalruleformat/color/
---
## HorizontalRuleFormat.Color property

Yatay kuralı dolduran fırça rengini alır veya ayarlar.

```csharp
public Color Color { get; set; }
```

### Notlar

Bu bir kısayolColor Emlak.

Varsayılan değer: Gray.

### Örnekler

Yatay bir kural şeklinin nasıl ekleneceğini ve biçimlendirmesinin nasıl özelleştirileceğini gösterir.

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

### Ayrıca bakınız

* class [HorizontalRuleFormat](../)
* ad alanı [Aspose.Words.Drawing](../../horizontalruleformat/)
* toplantı [Aspose.Words](../../../)


