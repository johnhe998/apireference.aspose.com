---
title: Stroke.On
second_title: Aspose.Words لمراجع .NET API
description: Stroke ملكية. يحدد ما إذا كان سيتم تحديد المسار.
type: docs
weight: 130
url: /ar/net/aspose.words.drawing/stroke/on/
---
## Stroke.On property

يحدد ما إذا كان سيتم تحديد المسار.

```csharp
public bool On { get; set; }
```

### ملاحظات

القيمة الافتراضية لـ[`Shape`](../../shape/) هو **حقيقي**.

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


