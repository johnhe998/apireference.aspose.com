---
title: ShapeBase.LocalToParent
second_title: Aspose.Words لمراجع .NET API
description: ShapeBase طريقة. تحويل قيمة من مساحة الإحداثيات المحلية إلى مساحة إحداثيات الشكل الأصلي.
type: docs
weight: 610
url: /ar/net/aspose.words.drawing/shapebase/localtoparent/
---
## ShapeBase.LocalToParent method

تحويل قيمة من مساحة الإحداثيات المحلية إلى مساحة إحداثيات الشكل الأصلي.

```csharp
public PointF LocalToParent(PointF value)
```

### أمثلة

يوضح كيفية ترجمة موقع إحداثيات x و y على مستوى إحداثي الشكل إلى موقع على مستوى إحداثي الشكل الأصل.

```csharp
Document doc = new Document();

// أدخل شكل مجموعة ، وضعه 100 نقطة أسفل وعلى يمين
// نقطة أصل إحداثيات x و Y الخاصة بالمستند.
GroupShape group = new GroupShape(doc);
group.Bounds = new RectangleF(100, 100, 500, 500);

// استخدم طريقة "LocalToParent" لتحديد ذلك (0 ، 0) على إحداثيات x و y الداخلية للمجموعة
// تقع على (100 ، 100) من نظام إحداثيات الشكل الأصل. أصل شكل المجموعة هو المستند نفسه.
Assert.AreEqual(new PointF(100, 100), group.LocalToParent(new PointF(0, 0)));

// بشكل افتراضي ، يكون مستوى الإحداثيات الداخلي للشكل أعلى الزاوية اليسرى عند (0 ، 0) ،
// والزاوية اليمنى السفلية عند (1000 ، 1000). نظرًا لحجمها ، فإن شكل مجموعتنا يغطي مساحة 500 نقطة × 500 نقطة
// في مستوى المستند. هذا يعني أنه سيتم ترجمة الحركة بمقدار 1 نقطة على مستوى إحداثي المستند
// لحركة 2 نقطة على مستوى إحداثيات شكل المجموعة.
Assert.AreEqual(new PointF(150, 150), group.LocalToParent(new PointF(100, 100)));
Assert.AreEqual(new PointF(200, 200), group.LocalToParent(new PointF(200, 200)));
Assert.AreEqual(new PointF(250, 250), group.LocalToParent(new PointF(300, 300)));

// انقل أصل المحور x و y لشكل المجموعة من الزاوية اليسرى العلوية إلى المركز.
// سيؤدي ذلك إلى موازنة الإحداثيات الداخلية للمجموعة المتعلقة بإحداثيات المستند بشكل أكبر.
group.CoordOrigin = new Point(-250, -250);

Assert.AreEqual(new PointF(375, 375), group.LocalToParent(new PointF(300, 300)));

// سيؤثر تغيير مقياس مستوى الإحداثيات أيضًا على المواقع النسبية.
group.CoordSize = new Size(500, 500);

Assert.AreEqual(new PointF(650, 650), group.LocalToParent(new PointF(300, 300)));

// إذا كنا نرغب في إضافة شكل إلى هذه المجموعة أثناء تحديد موقعها بناءً على موقع في المستند ،
// سنحتاج أولاً إلى تأكيد موقع في شكل المجموعة يتطابق مع موقع المستند.
Assert.AreEqual(new PointF(700, 700), group.LocalToParent(new PointF(350, 350)));

Shape shape = new Shape(doc, ShapeType.Rectangle)
{
    Width = 100,
    Height = 100,
    Left = 700,
    Top = 700
};

group.AppendChild(shape);
doc.FirstSection.Body.FirstParagraph.AppendChild(group);

doc.Save(ArtifactsDir + "Shape.LocalToParent.docx");
```

### أنظر أيضا

* class [ShapeBase](../)
* مساحة الاسم [Aspose.Words.Drawing](../../shapebase/)
* المجسم [Aspose.Words](../../../)


