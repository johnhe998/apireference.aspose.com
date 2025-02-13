---
title: ShapeBase.ZOrder
second_title: Aspose.Words لمراجع .NET API
description: ShapeBase ملكية. لتحديد ترتيب عرض الأشكال المتداخلة.
type: docs
weight: 550
url: /ar/net/aspose.words.drawing/shapebase/zorder/
---
## ShapeBase.ZOrder property

لتحديد ترتيب عرض الأشكال المتداخلة.

```csharp
public int ZOrder { get; set; }
```

### ملاحظات

له تأثير فقط لأشكال المستوى الأعلى.

القيمة الافتراضية هي 0.

يمثل الرقم أولوية التراص. سيتم عرض الشكل الذي يحتوي على رقم أعلى كما لو كان متداخلاً (في "مقدمة") شكل ذي رقم أقل.

يكون ترتيب الأشكال المتداخلة مستقلاً عن الأشكال الموجودة في الرأس وفي نص main للمستند.

يتم تحديد ترتيب عرض الأشكال الفرعية في شكل مجموعة بواسطة order داخل شكل المجموعة.

### أمثلة

يوضح كيفية التعامل مع ترتيب الأشكال.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// أدخل ثلاثة مستطيلات ملونة مختلفة تتداخل جزئيًا مع بعضها البعض.
// عندما نقوم بإدخال شكل يتداخل مع شكل آخر ، يضع Aspose.Words الشكل الأحدث أعلى الشكل القديم.
// سيتداخل المستطيل الأخضر الفاتح مع المستطيل الأزرق الفاتح ويحجبه جزئيًا ،
// وسيحجب المستطيل الأزرق الفاتح المستطيل البرتقالي.
Shape shape = builder.InsertShape(ShapeType.Rectangle, RelativeHorizontalPosition.LeftMargin, 100,
    RelativeVerticalPosition.TopMargin, 100, 200, 200, WrapType.None);
shape.FillColor = Color.Orange;

shape = builder.InsertShape(ShapeType.Rectangle, RelativeHorizontalPosition.LeftMargin, 150,
    RelativeVerticalPosition.TopMargin, 150, 200, 200, WrapType.None);
shape.FillColor = Color.LightBlue;

shape = builder.InsertShape(ShapeType.Rectangle, RelativeHorizontalPosition.LeftMargin, 200,
    RelativeVerticalPosition.TopMargin, 200, 200, 200, WrapType.None);
shape.FillColor = Color.LightGreen;

Shape[] shapes = doc.GetChildNodes(NodeType.Shape, true).OfType<Shape>().ToArray();

// تحدد خاصية "ZOrder" للشكل أولوية التكديس بين الأشكال المتداخلة الأخرى.
// إذا كان لشكلين متداخلين قيم "ZOrder" مختلفة ،
 // سيضع Microsoft Word الشكل بقيمة أعلى على الشكل ذي القيمة الأقل.
// قم بتعيين قيم "ZOrder" لأشكالنا لوضع المستطيل البرتقالي الأول فوق المستطيل الأزرق الفاتح الثاني
// والمستطيل الثاني باللون الأزرق الفاتح فوق المستطيل الأخضر الفاتح الثالث.
// سيؤدي هذا إلى عكس ترتيب التراص الأصلي.
shapes[0].ZOrder = 3;
shapes[1].ZOrder = 2;
shapes[2].ZOrder = 1;

doc.Save(ArtifactsDir + "Shape.ZOrder.docx");
```

### أنظر أيضا

* class [ShapeBase](../)
* مساحة الاسم [Aspose.Words.Drawing](../../shapebase/)
* المجسم [Aspose.Words](../../../)


