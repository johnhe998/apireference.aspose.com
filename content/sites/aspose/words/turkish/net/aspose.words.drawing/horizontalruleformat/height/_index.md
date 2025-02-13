---
title: HorizontalRuleFormat.Height
second_title: Aspose.Words for .NET API Referansı
description: HorizontalRuleFormat mülk. Yatay kuralın yüksekliğini alır veya ayarlar.
type: docs
weight: 30
url: /tr/net/aspose.words.drawing/horizontalruleformat/height/
---
## HorizontalRuleFormat.Height property

Yatay kuralın yüksekliğini alır veya ayarlar.

```csharp
public double Height { get; set; }
```

### istisnalar

| istisna | şart |
| --- | --- |
| ArgumentOutOfRangeException | Bağımsız değişken geçerli değerler aralığının dışında olduğunda atar. |

### Notlar

Bu bir kısayol[`Height`](../../shapebase/height/) Emlak.

Geçerli değerler 0 ile 1584 arasında değişir.

Varsayılan değer 1.5'tir.

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


