---
title: Class HorizontalRuleFormat
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.Drawing.HorizontalRuleFormat klass. Representerar horisontell regelformatering.
type: docs
weight: 920
url: /sv/net/aspose.words.drawing/horizontalruleformat/
---
## HorizontalRuleFormat class

Representerar horisontell regelformatering.

```csharp
public class HorizontalRuleFormat
```

## Egenskaper

| namn | Beskrivning |
| --- | --- |
| [Alignment](../../aspose.words.drawing/horizontalruleformat/alignment/) { get; set; } | Hämtar eller ställer in justeringen av den horisontella regeln. |
| [Color](../../aspose.words.drawing/horizontalruleformat/color/) { get; set; } | Hämtar eller ställer in penselfärgen som fyller den horisontella regeln. |
| [Height](../../aspose.words.drawing/horizontalruleformat/height/) { get; set; } | Hämtar eller ställer in höjden på den horisontella regeln. |
| [NoShade](../../aspose.words.drawing/horizontalruleformat/noshade/) { get; set; } | Indikerar närvaron av 3D-skuggning för den horisontella regeln. Om sant är den horisontella regeln utan 3D-skuggning och solid färg används. |
| [WidthPercent](../../aspose.words.drawing/horizontalruleformat/widthpercent/) { get; set; } | Hämtar eller ställer in längden på den angivna horisontella regeln uttryckt i procent av fönstrets bredd. |

### Exempel

Visar hur man infogar en horisontell regelform och anpassar dess formatering.

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

### Se även

* namnutrymme [Aspose.Words.Drawing](../../aspose.words.drawing/)
* hopsättning [Aspose.Words](../../)


