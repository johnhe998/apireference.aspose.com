---
title: ShapeBase.BoundsInPoints
second_title: Aspose.Words لمراجع .NET API
description: ShapeBase ملكية. الحصول على موقع وحجم الكتلة المحتوية للشكل بالنقاط  بالنسبة إلى مرساة الشكل العلوي .
type: docs
weight: 80
url: /ar/net/aspose.words.drawing/shapebase/boundsinpoints/
---
## ShapeBase.BoundsInPoints property

الحصول على موقع وحجم الكتلة المحتوية للشكل بالنقاط ، بالنسبة إلى مرساة الشكل العلوي .

```csharp
public RectangleF BoundsInPoints { get; }
```

### أمثلة

يوضح كيفية التحقق من الشكل الذي يحتوي على حدود الكتلة.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertShape(ShapeType.Line, RelativeHorizontalPosition.LeftMargin, 50,
    RelativeVerticalPosition.TopMargin, 50, 100, 100, WrapType.None);
shape.StrokeColor = Color.Orange;

// على الرغم من أن السطر نفسه يشغل مساحة صغيرة على صفحة المستند ،
// يحتل كتلة مستطيلة الشكل ، ويمكن تحديد حجمها باستخدام خصائص "الحدود".
Assert.AreEqual(new RectangleF(50, 50, 100, 100), shape.Bounds);
Assert.AreEqual(new RectangleF(50, 50, 100, 100), shape.BoundsInPoints);

// قم بإنشاء شكل مجموعة ، ثم قم بتعيين حجم الكتلة التي تحتوي عليها باستخدام خاصية "الحدود".
GroupShape group = new GroupShape(doc);
group.Bounds = new RectangleF(0, 100, 250, 250);

Assert.AreEqual(new RectangleF(0, 100, 250, 250), group.BoundsInPoints);

// قم بإنشاء مستطيل ، وتحقق من حجم الكتلة المحيطة به ، ثم قم بإضافته إلى شكل المجموعة.
shape = new Shape(doc, ShapeType.Rectangle)
{
    Width = 100,
    Height = 100,
    Left = 700,
    Top = 700
};

Assert.AreEqual(new RectangleF(700, 700, 100, 100), shape.BoundsInPoints);

group.AppendChild(shape);

// يوجد أصل مستوى إحداثيات المجموعة في الزاوية العلوية اليسرى من الكتلة التي تحتوي عليها ،
// وإحداثيات x و y لـ (1000 ، 1000) في الركن الأيمن السفلي.
// يبلغ حجم شكل مجموعتنا 250 × 250 نقطة ، لذا فإن كل 4 نقاط على مستوى إحداثي شكل المجموعة
// يترجم إلى 1 نقطة في المستوى الإحداثي لهيكل الوثيقة.
// كل شكل نقوم بإدراجه سيتقلص حجمه أيضًا بمعامل 4.
// سيعكس التغيير في خاصية "BoundsInPoints" الخاصة بالشكل هذا.
Assert.AreEqual(new RectangleF(175, 275, 25, 25), shape.BoundsInPoints);

doc.FirstSection.Body.FirstParagraph.AppendChild(group);

// أدخل شكلًا وضعه خارج حدود الكتلة التي تحتوي على شكل المجموعة.
shape = new Shape(doc, ShapeType.Rectangle)
{
    Width = 100,
    Height = 100,
    Left = 1000,
    Top = 1000
};

group.AppendChild(shape);

// زاد أثر شكل المجموعة في جسم المستند ، لكن الكتلة المحتوية تظل كما هي.
Assert.AreEqual(new RectangleF(0, 100, 250, 250), group.BoundsInPoints);
Assert.AreEqual(new RectangleF(250, 350, 25, 25), shape.BoundsInPoints);

doc.Save(ArtifactsDir + "Shape.Bounds.docx");
```

### أنظر أيضا

* class [ShapeBase](../)
* مساحة الاسم [Aspose.Words.Drawing](../../shapebase/)
* المجسم [Aspose.Words](../../../)


