---
title: ShapeBase.Bottom
second_title: Aspose.Words لمراجع .NET API
description: ShapeBase ملكية. الحصول على موضع الحافة السفلية للكتلة التي تحتوي على الشكل.
type: docs
weight: 60
url: /ar/net/aspose.words.drawing/shapebase/bottom/
---
## ShapeBase.Bottom property

الحصول على موضع الحافة السفلية للكتلة التي تحتوي على الشكل.

```csharp
public double Bottom { get; }
```

### ملاحظات

بالنسبة لشكل المستوى الأعلى ، تكون القيمة بالنقاط وتتناسب مع نقطة ارتساء الشكل.

بالنسبة للأشكال في مجموعة ، تكون القيمة في مساحة الإحداثيات ووحدات المجموعة الأصلية.

### أمثلة

يوضح كيفية إدراج صورة عائمة ، وتحديد موضعها وحجمها.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertImage(ImageDir + "Logo.jpg");
shape.WrapType = WrapType.None;

// تكوين خاصية "RelativeHorizontalPosition" للشكل لمعالجة قيمة الخاصية "Left"
 // كمسافة أفقية للشكل ، بالنقاط ، من الجانب الأيسر للصفحة.
shape.RelativeHorizontalPosition = RelativeHorizontalPosition.Page;

// اضبط المسافة الأفقية للشكل من الجانب الأيسر للصفحة على 100.
shape.Left = 100;

// استخدم خاصية "RelativeVerticalPosition" بطريقة مماثلة لوضع الشكل 80 نقطة أسفل أعلى الصفحة.
shape.RelativeVerticalPosition = RelativeVerticalPosition.Page;
shape.Top = 80;

// قم بتعيين ارتفاع الشكل ، والذي سيقيس العرض تلقائيًا للحفاظ على الأبعاد.
shape.Height = 125;

Assert.AreEqual(125.0d, shape.Width);

// تحتوي خصائص "الجزء السفلي" و "الأيمن" على الحواف السفلية واليمنى للصورة.
Assert.AreEqual(shape.Top + shape.Height, shape.Bottom);
Assert.AreEqual(shape.Left + shape.Width, shape.Right);

doc.Save(ArtifactsDir + "Image.CreateFloatingPositionSize.docx");
```

### أنظر أيضا

* class [ShapeBase](../)
* مساحة الاسم [Aspose.Words.Drawing](../../shapebase/)
* المجسم [Aspose.Words](../../../)


