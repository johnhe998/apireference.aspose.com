---
title: Class Stroke
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Drawing.Stroke فصل. يحدد حد لشكل .
type: docs
weight: 1160
url: /ar/net/aspose.words.drawing/stroke/
---
## Stroke class

يحدد حد لشكل .

```csharp
public class Stroke
```

## الخصائص

| اسم | وصف |
| --- | --- |
| [BackColor](../../aspose.words.drawing/stroke/backcolor/) { get; set; } | الحصول على لون خلفية الحد أو تعيينه . |
| [Color](../../aspose.words.drawing/stroke/color/) { get; set; } | يحدد لون ضربة الفرشاة . |
| [Color2](../../aspose.words.drawing/stroke/color2/) { get; set; } | يحدد لونًا ثانيًا لحد . |
| [DashStyle](../../aspose.words.drawing/stroke/dashstyle/) { get; set; } | يحدد نمط النقطة والشرطة لضربة . |
| [EndArrowLength](../../aspose.words.drawing/stroke/endarrowlength/) { get; set; } | يحدد طول رأس السهم لنهاية ضربة. |
| [EndArrowType](../../aspose.words.drawing/stroke/endarrowtype/) { get; set; } | يحدد رأس السهم لنهاية السكتة الدماغية . |
| [EndArrowWidth](../../aspose.words.drawing/stroke/endarrowwidth/) { get; set; } | يحدد عرض رأس السهم لنهاية ضربة فرشاة . |
| [EndCap](../../aspose.words.drawing/stroke/endcap/) { get; set; } | يحدد نمط الغطاء لنهاية السكتة الدماغية . |
| [ForeColor](../../aspose.words.drawing/stroke/forecolor/) { get; set; } | الحصول على أو تحديد لون المقدمة للضربة . |
| [ImageBytes](../../aspose.words.drawing/stroke/imagebytes/) { get; } | يحدد الصورة لصورة الحد أو تعبئة النقش . |
| [JoinStyle](../../aspose.words.drawing/stroke/joinstyle/) { get; set; } | يحدد نمط الانضمام لخطوط متعددة . |
| [LineStyle](../../aspose.words.drawing/stroke/linestyle/) { get; set; } | يحدد نمط الخط للسكتة الدماغية . |
| [On](../../aspose.words.drawing/stroke/on/) { get; set; } | يحدد ما إذا كان سيتم تحديد المسار. |
| [Opacity](../../aspose.words.drawing/stroke/opacity/) { get; set; } | يحدد مقدار شفافية ضربة الفرشاة. النطاق الصالح هو من 0 إلى 1. |
| [StartArrowLength](../../aspose.words.drawing/stroke/startarrowlength/) { get; set; } | يحدد طول رأس السهم لبداية ضربة. |
| [StartArrowType](../../aspose.words.drawing/stroke/startarrowtype/) { get; set; } | يحدد رأس السهم لبداية ضربة . |
| [StartArrowWidth](../../aspose.words.drawing/stroke/startarrowwidth/) { get; set; } | يحدد عرض رأس السهم لبداية ضربة. |
| [Transparency](../../aspose.words.drawing/stroke/transparency/) { get; set; } | الحصول على أو تعيين قيمة بين 0.0 (معتم) و 1.0 (واضح) تمثل درجة الشفافية للحد . |
| [Visible](../../aspose.words.drawing/stroke/visible/) { get; set; } | الحصول على أو تعيين علامة تشير إلى ما إذا كانت ضربة الفرشاة مرئية . |
| [Weight](../../aspose.words.drawing/stroke/weight/) { get; set; } | يحدد سماكة الفرشاة التي تضرب مسار الشكل بالنقاط. |

### ملاحظات

استخدم ال[`Stroke`](../shape/stroke/)للوصول إلى خصائص ضغط الشكل . لا يمكنك إنشاء مثيلات لملف`Stroke` فئة مباشرة.

### أمثلة

يوضح كيفية تغيير خصائص ضربة الفرشاة.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertShape(ShapeType.Rectangle, RelativeHorizontalPosition.LeftMargin, 100,
    RelativeVerticalPosition.TopMargin, 100, 200, 200, WrapType.None);

// الأشكال الأساسية ، مثل المستطيل ، لها جزأين مرئيين.
// 1 - التعبئة ، التي تنطبق على المنطقة داخل المخطط التفصيلي للشكل:
shape.Fill.ForeColor = Color.White;

// 2 - الحد الذي يحدد مخطط الشكل:
// تعديل الخصائص المختلفة لضربة هذا الشكل.
Stroke stroke = shape.Stroke;
stroke.On = true;
stroke.Weight = 5;
stroke.Color = Color.Red;
stroke.DashStyle = DashStyle.ShortDashDotDot;
stroke.JoinStyle = JoinStyle.Miter;
stroke.EndCap = EndCap.Square;
stroke.LineStyle = ShapeLineStyle.Triple;

doc.Save(ArtifactsDir + "Shape.Stroke.docx");
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words.Drawing](../../aspose.words.drawing/)
* المجسم [Aspose.Words](../../)


