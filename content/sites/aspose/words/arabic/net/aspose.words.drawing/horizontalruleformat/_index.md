---
title: Class HorizontalRuleFormat
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Drawing.HorizontalRuleFormat فصل. يمثل تنسيق القاعدة الأفقية .
type: docs
weight: 920
url: /ar/net/aspose.words.drawing/horizontalruleformat/
---
## HorizontalRuleFormat class

يمثل تنسيق القاعدة الأفقية .

```csharp
public class HorizontalRuleFormat
```

## الخصائص

| اسم | وصف |
| --- | --- |
| [Alignment](../../aspose.words.drawing/horizontalruleformat/alignment/) { get; set; } | الحصول على محاذاة القاعدة الأفقية أو تعيينها. |
| [Color](../../aspose.words.drawing/horizontalruleformat/color/) { get; set; } | الحصول على أو تعيين لون الفرشاة الذي يملأ القاعدة الأفقية. |
| [Height](../../aspose.words.drawing/horizontalruleformat/height/) { get; set; } | الحصول على أو تحديد ارتفاع القاعدة الأفقية. |
| [NoShade](../../aspose.words.drawing/horizontalruleformat/noshade/) { get; set; } | يشير إلى وجود تظليل ثلاثي الأبعاد للقاعدة الأفقية . إذا كان هذا صحيحًا ، فإن القاعدة الأفقية بدون تظليل ثلاثي الأبعاد ويتم استخدام لون خالص . |
| [WidthPercent](../../aspose.words.drawing/horizontalruleformat/widthpercent/) { get; set; } | الحصول على أو تحديد طول القاعدة الأفقية المحددة كنسبة مئوية من عرض النافذة. |

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

* مساحة الاسم [Aspose.Words.Drawing](../../aspose.words.drawing/)
* المجسم [Aspose.Words](../../)


