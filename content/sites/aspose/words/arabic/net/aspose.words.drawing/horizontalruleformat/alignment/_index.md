---
title: HorizontalRuleFormat.Alignment
second_title: Aspose.Words لمراجع .NET API
description: HorizontalRuleFormat ملكية. الحصول على محاذاة القاعدة الأفقية أو تعيينها.
type: docs
weight: 10
url: /ar/net/aspose.words.drawing/horizontalruleformat/alignment/
---
## HorizontalRuleFormat.Alignment property

الحصول على محاذاة القاعدة الأفقية أو تعيينها.

```csharp
public HorizontalRuleAlignment Alignment { get; set; }
```

### ملاحظات

النظام الأساسيLeft.

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

* enum [HorizontalRuleAlignment](../../horizontalrulealignment/)
* class [HorizontalRuleFormat](../)
* مساحة الاسم [Aspose.Words.Drawing](../../horizontalruleformat/)
* المجسم [Aspose.Words](../../../)


