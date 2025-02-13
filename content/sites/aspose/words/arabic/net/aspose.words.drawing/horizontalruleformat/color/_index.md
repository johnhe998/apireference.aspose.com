---
title: HorizontalRuleFormat.Color
second_title: Aspose.Words لمراجع .NET API
description: HorizontalRuleFormat ملكية. الحصول على أو تعيين لون الفرشاة الذي يملأ القاعدة الأفقية.
type: docs
weight: 20
url: /ar/net/aspose.words.drawing/horizontalruleformat/color/
---
## HorizontalRuleFormat.Color property

الحصول على أو تعيين لون الفرشاة الذي يملأ القاعدة الأفقية.

```csharp
public Color Color { get; set; }
```

### ملاحظات

هذا هو اختصار لملفColor منشأه.

القيمة الافتراضية هي Gray.

### أمثلة

يوضح كيفية إدراج شكل تسطير أفقي ، وتخصيص تنسيقه.

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

### أنظر أيضا

* class [HorizontalRuleFormat](../)
* مساحة الاسم [Aspose.Words.Drawing](../../horizontalruleformat/)
* المجسم [Aspose.Words](../../../)


