---
title: ShapeBase.FlipOrientation
second_title: Aspose.Words لمراجع .NET API
description: ShapeBase ملكية. يبدل اتجاه الشكل.
type: docs
weight: 180
url: /ar/net/aspose.words.drawing/shapebase/fliporientation/
---
## ShapeBase.FlipOrientation property

يبدل اتجاه الشكل.

```csharp
public FlipOrientation FlipOrientation { get; set; }
```

### ملاحظات

النظام الأساسيNone.

### أمثلة

يوضح كيفية قلب شكل على محور.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// أدخل شكل صورة واترك اتجاهه في حالته الافتراضية.
Shape shape = builder.InsertShape(ShapeType.Rectangle, RelativeHorizontalPosition.LeftMargin, 100,
    RelativeVerticalPosition.TopMargin, 100, 100, 100, WrapType.None);
shape.ImageData.SetImage(ImageDir + "Logo.jpg");

Assert.AreEqual(FlipOrientation.None, shape.FlipOrientation);

shape = builder.InsertShape(ShapeType.Rectangle, RelativeHorizontalPosition.LeftMargin, 250,
    RelativeVerticalPosition.TopMargin, 100, 100, 100, WrapType.None);
shape.ImageData.SetImage(ImageDir + "Logo.jpg");

// اضبط خاصية FlipOrientation على FlipOrientation.Horizontal لقلب الشكل الثاني على المحور y ،
// تحويلها إلى صورة معكوسة أفقية للشكل الأول.
shape.FlipOrientation = FlipOrientation.Horizontal;

shape = builder.InsertShape(ShapeType.Rectangle, RelativeHorizontalPosition.LeftMargin, 100,
    RelativeVerticalPosition.TopMargin, 250, 100, 100, WrapType.None);
shape.ImageData.SetImage(ImageDir + "Logo.jpg");

// اضبط خاصية FlipOrientation على FlipOrientation.Horizontal لقلب الشكل الثالث على المحور x ،
// تحويلها إلى صورة معكوسة عمودية للشكل الأول.
shape.FlipOrientation = FlipOrientation.Vertical;

shape = builder.InsertShape(ShapeType.Rectangle, RelativeHorizontalPosition.LeftMargin, 250,
    RelativeVerticalPosition.TopMargin, 250, 100, 100, WrapType.None);
shape.ImageData.SetImage(ImageDir + "Logo.jpg");

// اضبط خاصية "FlipOrientation" على "FlipOrientation.Horizontal" لقلب الشكل الرابع على كل من محوري x و y ،
// تحويلها إلى صورة معكوسة أفقية ورأسية للشكل الأول.
shape.FlipOrientation = FlipOrientation.Both;

doc.Save(ArtifactsDir + "Shape.FlipShapeOrientation.docx");
```

### أنظر أيضا

* enum [FlipOrientation](../../fliporientation/)
* class [ShapeBase](../)
* مساحة الاسم [Aspose.Words.Drawing](../../shapebase/)
* المجسم [Aspose.Words](../../../)


