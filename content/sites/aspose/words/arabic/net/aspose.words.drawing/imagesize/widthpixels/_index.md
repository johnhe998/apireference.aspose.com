---
title: ImageSize.WidthPixels
second_title: Aspose.Words لمراجع .NET API
description: ImageSize ملكية. يحصل على عرض الصورة بالبكسل.
type: docs
weight: 60
url: /ar/net/aspose.words.drawing/imagesize/widthpixels/
---
## ImageSize.WidthPixels property

يحصل على عرض الصورة بالبكسل.

```csharp
public int WidthPixels { get; }
```

### أمثلة

يوضح كيفية قراءة خصائص صورة في شكل.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// أدخل شكلاً في المستند الذي يحتوي على صورة مأخوذة من نظام الملفات المحلي لدينا.
Shape shape = builder.InsertImage(ImageDir + "Logo.jpg");

// إذا كان الشكل يحتوي على صورة ، فستكون خاصية ImageData الخاصة به صالحة ،
// وسيحتوي على كائن ImageSize.
ImageSize imageSize = shape.ImageData.ImageSize; 

// يحتوي كائن ImageSize على معلومات للقراءة فقط حول الصورة داخل الشكل.
Assert.AreEqual(400, imageSize.HeightPixels);
Assert.AreEqual(400, imageSize.WidthPixels);

const double delta = 0.05;
Assert.AreEqual(95.98d, imageSize.HorizontalResolution, delta);
Assert.AreEqual(95.98d, imageSize.VerticalResolution, delta);

// يمكننا أن نبني حجم الشكل على حجم صورته لتجنب تمدد الصورة.
shape.Width = imageSize.WidthPoints * 2;
shape.Height = imageSize.HeightPoints * 2;

doc.Save(ArtifactsDir + "Drawing.ImageSize.docx");
```

### أنظر أيضا

* class [ImageSize](../)
* مساحة الاسم [Aspose.Words.Drawing](../../imagesize/)
* المجسم [Aspose.Words](../../../)


