---
title: Class GradientStopCollection
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Drawing.GradientStopCollection فصل. يحتوي على مجموعة منGradientStop الكائنات .
type: docs
weight: 860
url: /ar/net/aspose.words.drawing/gradientstopcollection/
---
## GradientStopCollection class

يحتوي على مجموعة من[`GradientStop`](../gradientstop/) الكائنات .

```csharp
public class GradientStopCollection : IEnumerable<GradientStop>
```

## الخصائص

| اسم | وصف |
| --- | --- |
| [Count](../../aspose.words.drawing/gradientstopcollection/count/) { get; } | الحصول على قيمة عددية تشير إلى عدد العناصر في المجموعة. |
| [Item](../../aspose.words.drawing/gradientstopcollection/item/) { get; set; } | يحصل أو يحدد أ[`GradientStop`](../gradientstop/) كائن في المجموعة . |

## طُرق

| اسم | وصف |
| --- | --- |
| [Add](../../aspose.words.drawing/gradientstopcollection/add/)(GradientStop) | يضيف محددًا[`GradientStop`](../gradientstop/) إلى التدرج اللوني . |
| [GetEnumerator](../../aspose.words.drawing/gradientstopcollection/getenumerator/)() | إرجاع عداد يتكرر خلال المجموعة. |
| [Insert](../../aspose.words.drawing/gradientstopcollection/insert/)(int, GradientStop) | إدراج أ[`GradientStop`](../gradientstop/) إلى المجموعة في فهرس محدد. |
| [Remove](../../aspose.words.drawing/gradientstopcollection/remove/)(GradientStop) | يزيل ملف[`GradientStop`](../gradientstop/) من المجموعة. |
| [RemoveAt](../../aspose.words.drawing/gradientstopcollection/removeat/)(int) | يزيل أ[`GradientStop`](../gradientstop/)من المجموعة في فهرس محدد. |

### ملاحظات

لا يمكنك إنشاء مثيلات من هذه الفئة مباشرةً. استخدم ملف[`GradientStops`](../fill/gradientstops/) خاصية للوصول إلى التوقفات المتدرجة لكائنات التعبئة.

### أمثلة

يوضح كيفية إضافة نقاط توقف متدرجة لتعبئة التدرج.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertShape(ShapeType.Rectangle, 80, 80);
shape.Fill.TwoColorGradient(Color.Green, Color.Red, GradientStyle.Horizontal, GradientVariant.Variant2);

// احصل على مجموعة نقاط التدرج.
GradientStopCollection gradientStops = shape.Fill.GradientStops;

// تغيير أول توقف متدرج.
gradientStops[0].Color = Color.Aqua;
gradientStops[0].Position = 0.1;
gradientStops[0].Transparency = 0.25;

// أضف نقطة توقف متدرجة جديدة إلى نهاية المجموعة.
GradientStop gradientStop = new GradientStop(Color.Brown, 0.5);
gradientStops.Add(gradientStop);

// إزالة توقف التدرج عند الفهرس 1.
gradientStops.RemoveAt(1);
// وأدخل نقطة توقف متدرجة جديدة في نفس الفهرس 1.
gradientStops.Insert(1, new GradientStop(Color.Chocolate, 0.75, 0.3));

// إزالة آخر توقف متدرج في المجموعة.
gradientStop = gradientStops[2];
gradientStops.Remove(gradientStop);

Assert.AreEqual(2, gradientStops.Count);

Assert.AreEqual(Color.Aqua.ToArgb(), gradientStops[0].Color.ToArgb());
Assert.AreEqual(0.1d, gradientStops[0].Position, 0.01d);
Assert.AreEqual(0.25d, gradientStops[0].Transparency, 0.01d);

Assert.AreEqual(Color.Chocolate.ToArgb(), gradientStops[1].Color.ToArgb());
Assert.AreEqual(0.75d, gradientStops[1].Position, 0.01d);
Assert.AreEqual(0.3d, gradientStops[1].Transparency, 0.01d);

// استخدم خيار التوافق لتحديد الشكل باستخدام DML
// إذا كنت تريد الحصول على خاصية "GradientStops" بعد حفظ المستند.
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Strict };

doc.Save(ArtifactsDir + "Shape.GradientStops.docx", saveOptions);
```

### أنظر أيضا

* class [GradientStop](../gradientstop/)
* مساحة الاسم [Aspose.Words.Drawing](../../aspose.words.drawing/)
* المجسم [Aspose.Words](../../)


