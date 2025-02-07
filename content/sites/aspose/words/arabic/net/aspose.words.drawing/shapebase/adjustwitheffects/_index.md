---
title: ShapeBase.AdjustWithEffects
second_title: Aspose.Words لمراجع .NET API
description: ShapeBase طريقة. يضيف إلى قيم مستطيل المصدر لمدى التأثير ويعيد المستطيل النهائي.
type: docs
weight: 560
url: /ar/net/aspose.words.drawing/shapebase/adjustwitheffects/
---
## ShapeBase.AdjustWithEffects method

يضيف إلى قيم مستطيل المصدر لمدى التأثير ويعيد المستطيل النهائي.

```csharp
public RectangleF AdjustWithEffects(RectangleF source)
```

### أمثلة

يوضح كيفية التحقق من كيفية تأثر حدود الشكل بتأثيرات الشكل.

```csharp
Document doc = new Document(MyDir + "Shape shadow effect.docx");

Shape[] shapes = doc.GetChildNodes(NodeType.Shape, true).OfType<Shape>().ToArray();

Assert.AreEqual(2, shapes.Length);

// الشكلان متطابقان من حيث الأبعاد ونوع الشكل.
Assert.AreEqual(shapes[0].Width, shapes[1].Width);
Assert.AreEqual(shapes[0].Height, shapes[1].Height);
Assert.AreEqual(shapes[0].ShapeType, shapes[1].ShapeType);

// الشكل الأول ليس له تأثيرات ، والشكل الثاني له ظل ومخطط سميك.
// تجعل هذه التأثيرات حجم الصورة الظلية للشكل الثاني أكبر من حجم الشكل الأول.
// على الرغم من ظهور حجم المستطيل عند النقر فوق هذه الأشكال في Microsoft Word ،
// تتأثر الحدود الخارجية المرئية للشكل الثاني بالظل والمخطط وبالتالي تكون أكبر.
// يمكننا استخدام طريقة "AdjustWithEffects" لمعرفة الحجم الحقيقي للشكل.
Assert.AreEqual(0.0, shapes[0].StrokeWeight);
Assert.AreEqual(20.0, shapes[1].StrokeWeight);
Assert.False(shapes[0].ShadowEnabled);
Assert.True(shapes[1].ShadowEnabled);

Shape shape = shapes[0];

// قم بإنشاء كائن RectangleF ، يمثل مستطيلاً ،
// التي يمكن أن نستخدمها كإحداثيات وحدود للشكل.
RectangleF rectangleF = new RectangleF(200, 200, 1000, 1000);

// قم بتشغيل هذه الطريقة لتعديل حجم المستطيل لجميع تأثيرات الشكل لدينا.
RectangleF rectangleFOut = shape.AdjustWithEffects(rectangleF);

// نظرًا لأن الشكل ليس له تأثيرات متغيرة للحدود ، فإن أبعاده الحدية لا تتأثر.
Assert.AreEqual(200, rectangleFOut.X);
Assert.AreEqual(200, rectangleFOut.Y);
Assert.AreEqual(1000, rectangleFOut.Width);
Assert.AreEqual(1000, rectangleFOut.Height);

// تحقق من المدى النهائي للشكل الأول بالنقاط.
Assert.AreEqual(0, shape.BoundsWithEffects.X);
Assert.AreEqual(0, shape.BoundsWithEffects.Y);
Assert.AreEqual(147, shape.BoundsWithEffects.Width);
Assert.AreEqual(147, shape.BoundsWithEffects.Height);

shape = shapes[1];
rectangleF = new RectangleF(200, 200, 1000, 1000);
rectangleFOut = shape.AdjustWithEffects(rectangleF);

// لقد نقلت تأثيرات الشكل الزاوية اليسرى العلوية الظاهرة من الشكل قليلاً.
Assert.AreEqual(171.5, rectangleFOut.X);
Assert.AreEqual(167, rectangleFOut.Y);

// أثرت التأثيرات أيضًا على الأبعاد المرئية للشكل.
Assert.AreEqual(1045, rectangleFOut.Width);
Assert.AreEqual(1132, rectangleFOut.Height);

// أثرت التأثيرات أيضًا على الحدود المرئية للشكل.
Assert.AreEqual(-28.5, shape.BoundsWithEffects.X);
Assert.AreEqual(-33, shape.BoundsWithEffects.Y);
Assert.AreEqual(192, shape.BoundsWithEffects.Width);
Assert.AreEqual(279, shape.BoundsWithEffects.Height);
```

### أنظر أيضا

* class [ShapeBase](../)
* مساحة الاسم [Aspose.Words.Drawing](../../shapebase/)
* المجسم [Aspose.Words](../../../)


