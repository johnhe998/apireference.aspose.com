---
title: ShapeBase.RelativeVerticalPosition
second_title: Aspose.Words لمراجع .NET API
description: ShapeBase ملكية. تحديد متعلق بالموضع الرأسي للشكل.
type: docs
weight: 410
url: /ar/net/aspose.words.drawing/shapebase/relativeverticalposition/
---
## ShapeBase.RelativeVerticalPosition property

تحديد متعلق بالموضع الرأسي للشكل.

```csharp
public RelativeVerticalPosition RelativeVerticalPosition { get; set; }
```

### ملاحظات

النظام الأساسيParagraph.

له تأثير فقط للأشكال العائمة ذات المستوى الأعلى.

### أمثلة

يوضح كيفية إدراج صورة عائمة في وسط الصفحة.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// أدخل صورة عائمة ستظهر خلف النص المتداخل وقم بمحاذاة مركز الصفحة.
Shape shape = builder.InsertImage(ImageDir + "Logo.jpg");
shape.WrapType = WrapType.None;
shape.BehindText = true;
shape.RelativeHorizontalPosition = RelativeHorizontalPosition.Page;
shape.RelativeVerticalPosition = RelativeVerticalPosition.Page;
shape.HorizontalAlignment = HorizontalAlignment.Center;
shape.VerticalAlignment = VerticalAlignment.Center;

doc.Save(ArtifactsDir + "Image.CreateFloatingPageCenter.docx");
```

### أنظر أيضا

* enum [RelativeVerticalPosition](../../relativeverticalposition/)
* class [ShapeBase](../)
* مساحة الاسم [Aspose.Words.Drawing](../../shapebase/)
* المجسم [Aspose.Words](../../../)


