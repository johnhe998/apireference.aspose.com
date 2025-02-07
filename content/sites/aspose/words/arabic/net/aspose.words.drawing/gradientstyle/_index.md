---
title: Enum GradientStyle
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Drawing.GradientStyle تعداد. تحديد نمط التعبئة المتدرجة .
type: docs
weight: 870
url: /ar/net/aspose.words.drawing/gradientstyle/
---
## GradientStyle enumeration

تحديد نمط التعبئة المتدرجة .

```csharp
public enum GradientStyle
```

### قيم

| اسم | قيمة | وصف |
| --- | --- | --- |
| None | `-1` | لا يوجد تدرج . |
| Horizontal | `1` | تشغيل التدرج أفقيًا عبر كائن . |
| Vertical | `2` | جري التدرج رأسيًا لأسفل كائن . |
| DiagonalUp | `3` | تدرج لوني قطري يتحرك من الزاوية السفلية إلى الزاوية المقابلة. |
| DiagonalDown | `4` | تدرج لوني قطري يتحرك من الزاوية العلوية لأسفل إلى الزاوية المقابلة . |
| FromCorner | `5` | تدرج متدرج من زاوية إلى الزوايا الثلاث الأخرى. |
| FromCenter | `6` | التدرج المتدرج من المركز إلى الزوايا . |

### أمثلة

يوضح كيفية تعبئة شكل بتدرجات لونية.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertShape(ShapeType.Rectangle, 80, 80);
// قم بتطبيق تعبئة متدرجة بلون واحد على الشكل باستخدام لون تعبئة متدرج.
shape.Fill.OneColorGradient(Color.Red, GradientStyle.Horizontal, GradientVariant.Variant2, 0.1);

Assert.AreEqual(Color.Red.ToArgb(), shape.Fill.ForeColor.ToArgb());
Assert.AreEqual(GradientStyle.Horizontal, shape.Fill.GradientStyle);
Assert.AreEqual(GradientVariant.Variant2, shape.Fill.GradientVariant);
Assert.AreEqual(270, shape.Fill.GradientAngle);

shape = builder.InsertShape(ShapeType.Rectangle, 80, 80);
// تطبيق تعبئة متدرجة ثنائية اللون على الشكل.
shape.Fill.TwoColorGradient(GradientStyle.FromCorner, GradientVariant.Variant4);
// تغيير لون الخلفية للتعبئة المتدرجة.
shape.Fill.BackColor = Color.Yellow;
// لاحظ أن التغييرات "GradientAngle" إلى "GradientStyle.FromCorner / GradientStyle.FromCenter"
// لا تحصل التعبئة المتدرجة على أي تأثير ، وستعمل فقط مع التدرج الخطي.
shape.Fill.GradientAngle = 15;

Assert.AreEqual(Color.Yellow.ToArgb(), shape.Fill.BackColor.ToArgb());
Assert.AreEqual(GradientStyle.FromCorner, shape.Fill.GradientStyle);
Assert.AreEqual(GradientVariant.Variant4, shape.Fill.GradientVariant);
Assert.AreEqual(0, shape.Fill.GradientAngle);

// استخدم خيار التوافق لتحديد الشكل باستخدام DML إذا كنت تريد الحصول على "GradientStyle" ،
// خصائص "GradientVariant" و "GradientAngle" بعد حفظ المستند.
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Strict };

doc.Save(ArtifactsDir + "Shape.GradientFill.docx", saveOptions);
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words.Drawing](../../aspose.words.drawing/)
* المجسم [Aspose.Words](../../)


