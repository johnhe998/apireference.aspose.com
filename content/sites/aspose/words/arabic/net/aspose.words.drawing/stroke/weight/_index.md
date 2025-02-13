---
title: Stroke.Weight
second_title: Aspose.Words لمراجع .NET API
description: Stroke ملكية. يحدد سماكة الفرشاة التي تضرب مسار الشكل بالنقاط.
type: docs
weight: 200
url: /ar/net/aspose.words.drawing/stroke/weight/
---
## Stroke.Weight property

يحدد سماكة الفرشاة التي تضرب مسار الشكل بالنقاط.

```csharp
public double Weight { get; set; }
```

### ملاحظات

القيمة الافتراضية لـ[`Shape`](../../shape/) هو 0.75.

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

* class [Stroke](../)
* مساحة الاسم [Aspose.Words.Drawing](../../stroke/)
* المجسم [Aspose.Words](../../../)


