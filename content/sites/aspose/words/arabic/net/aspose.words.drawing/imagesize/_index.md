---
title: Class ImageSize
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Drawing.ImageSize فصل. يحتوي على معلومات حول حجم الصورة ودقتها .
type: docs
weight: 940
url: /ar/net/aspose.words.drawing/imagesize/
---
## ImageSize class

يحتوي على معلومات حول حجم الصورة ودقتها .

```csharp
public class ImageSize
```

## المنشئون

| اسم | وصف |
| --- | --- |
| [ImageSize](imagesize/#constructor)(int, int) | يقوم بتهيئة العرض والارتفاع للقيم المحددة بالبكسل. يقوم بتهيئة الدقة إلى 96 نقطة في البوصة. _ |
| [ImageSize](imagesize/#constructor_1)(int, int, double, double) | يقوم بتهيئة العرض والارتفاع والدقة للقيم المحددة. |

## الخصائص

| اسم | وصف |
| --- | --- |
| [HeightPixels](../../aspose.words.drawing/imagesize/heightpixels/) { get; } | الحصول على ارتفاع الصورة بالبكسل . |
| [HeightPoints](../../aspose.words.drawing/imagesize/heightpoints/) { get; } | يحصل على ارتفاع الصورة بالنقاط. 1 نقطة 1/72 بوصة. |
| [HorizontalResolution](../../aspose.words.drawing/imagesize/horizontalresolution/) { get; } | الحصول على الدقة الأفقية في DPI. |
| [VerticalResolution](../../aspose.words.drawing/imagesize/verticalresolution/) { get; } | الحصول على الدقة الرأسية في DPI. |
| [WidthPixels](../../aspose.words.drawing/imagesize/widthpixels/) { get; } | يحصل على عرض الصورة بالبكسل. |
| [WidthPoints](../../aspose.words.drawing/imagesize/widthpoints/) { get; } | يحصل على عرض الصورة بالنقاط. 1 نقطة 1/72 بوصة. |

### أمثلة

يوضح كيفية تغيير حجم الشكل بصورة.

```csharp
#if NET48 || JAVA
            Image image = Image.FromFile(ImageDir + "Logo.jpg");

            Assert.AreEqual(400, image.Size.Width);
            Assert.AreEqual(400, image.Size.Height);
#elif NET5_0_OR_GREATER
            SKBitmap image = SKBitmap.Decode(ImageDir + "Logo.jpg");

            Assert.AreEqual(400, image.Width);
            Assert.AreEqual(400, image.Height);
#endif

            // عندما نقوم بإدخال صورة باستخدام طريقة "InsertImage" ، يقوم المنشئ بقياس الشكل الذي يعرض الصورة بحيث ،
            // عندما نعرض المستند باستخدام تكبير بنسبة 100٪ في Microsoft Word ، يعرض الشكل الصورة بحجمها الفعلي.
            Document doc = new Document();
            DocumentBuilder builder = new DocumentBuilder(doc);
            Shape shape = builder.InsertImage(ImageDir + "Logo.jpg");

            // ستؤدي الصورة مقاس 400 × 400 إلى إنشاء كائن ImageData بحجم صورة 300 × 300 نقطة.
            ImageSize imageSize = shape.ImageData.ImageSize;

            Assert.AreEqual(300.0d, imageSize.WidthPoints);
            Assert.AreEqual(300.0d, imageSize.HeightPoints);

            // إذا كانت أبعاد الشكل تتطابق مع أبعاد بيانات الصورة ،
            // ثم يعرض الشكل الصورة بحجمها الأصلي.
            Assert.AreEqual(300.0d, shape.Width);
            Assert.AreEqual(300.0d, shape.Height);

             // تصغير الحجم الكلي للشكل بنسبة 50٪.
            shape.Width *= 0.5;

             // تنطبق عوامل القياس على كل من العرض والارتفاع في نفس الوقت للحفاظ على تناسب الشكل.
            Assert.AreEqual(150.0d, shape.Width);
            Assert.AreEqual(150.0d, shape.Height);

            // عندما نغير حجم الشكل ، يظل حجم بيانات الصورة كما هو.
            Assert.AreEqual(300.0d, imageSize.WidthPoints);
            Assert.AreEqual(300.0d, imageSize.HeightPoints);

            // يمكننا الرجوع إلى أبعاد بيانات الصورة لتطبيق مقياس بناءً على حجم الصورة.
            shape.Width = imageSize.WidthPoints * 1.1;

            Assert.AreEqual(330.0d, shape.Width);
            Assert.AreEqual(330.0d, shape.Height);

            doc.Save(ArtifactsDir + "Image.ScaleImage.docx");
```

### أنظر أيضا

* property [ImageSize](../imagedata/imagesize/)
* مساحة الاسم [Aspose.Words.Drawing](../../aspose.words.drawing/)
* المجسم [Aspose.Words](../../)


