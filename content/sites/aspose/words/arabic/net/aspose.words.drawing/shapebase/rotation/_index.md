---
title: ShapeBase.Rotation
second_title: Aspose.Words لمراجع .NET API
description: ShapeBase ملكية. يحدد الزاوية بالدرجات التي يتم تدوير الشكل بها. _ القيمة الموجبة تقابل زاوية الدوران في اتجاه عقارب الساعة .
type: docs
weight: 430
url: /ar/net/aspose.words.drawing/shapebase/rotation/
---
## ShapeBase.Rotation property

يحدد الزاوية (بالدرجات) التي يتم تدوير الشكل بها. _ القيمة الموجبة تقابل زاوية الدوران في اتجاه عقارب الساعة .

```csharp
public double Rotation { get; set; }
```

### ملاحظات

القيمة الافتراضية هي 0.

### أمثلة

يوضح كيفية إدراج وتدوير صورة.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// أدخل شكل مع صورة.
Shape shape = builder.InsertImage(Image.FromFile(ImageDir + "Logo.jpg"));
Assert.True(shape.CanHaveImage);
Assert.True(shape.HasImage);

// تدوير الصورة 45 درجة في اتجاه عقارب الساعة.
shape.Rotation = 45;

doc.Save(ArtifactsDir + "Shape.Rotate.docx");
```

### أنظر أيضا

* class [ShapeBase](../)
* مساحة الاسم [Aspose.Words.Drawing](../../shapebase/)
* المجسم [Aspose.Words](../../../)


