---
title: HorizontalRuleFormat.Color
second_title: Aspose.Words för .NET API Referens
description: HorizontalRuleFormat fast egendom. Hämtar eller ställer in penselfärgen som fyller den horisontella regeln.
type: docs
weight: 20
url: /sv/net/aspose.words.drawing/horizontalruleformat/color/
---
## HorizontalRuleFormat.Color property

Hämtar eller ställer in penselfärgen som fyller den horisontella regeln.

```csharp
public Color Color { get; set; }
```

### Anmärkningar

Detta är en genväg tillColor fast egendom.

Standardvärdet är Gray.

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

* class [HorizontalRuleFormat](../)
* namnutrymme [Aspose.Words.Drawing](../../horizontalruleformat/)
* hopsättning [Aspose.Words](../../../)


