---
title: ImageSaveOptions.TiffBinarizationMethod
second_title: Aspose.Words لمراجع .NET API
description: ImageSaveOptions ملكية. الحصول على أو تعيين الطريقة المستخدمة أثناء تحويل الصور إلى تنسيق 1 bpp عندماSaveFormat هو SaveFormat.Tiff and TiffCompression يساوي TiffCompression.Ccitt3 أو TiffCompression.Ccitt4.
type: docs
weight: 160
url: /ar/net/aspose.words.saving/imagesaveoptions/tiffbinarizationmethod/
---
## ImageSaveOptions.TiffBinarizationMethod property

الحصول على أو تعيين الطريقة المستخدمة أثناء تحويل الصور إلى تنسيق 1 bpp عندما[`SaveFormat`](../saveformat/) هو SaveFormat.Tiff and [`TiffCompression`](../tiffcompression/) يساوي TiffCompression.Ccitt3 أو TiffCompression.Ccitt4.

```csharp
public ImageBinarizationMethod TiffBinarizationMethod { get; set; }
```

### ملاحظات

القيمة الافتراضية هي ImageBinarizationMethod.Threshold.

### أمثلة

يوضح كيفية تعيين حد خطأ TIFF الثنائي عند استخدام طريقة Floyd-Steinberg لعرض صورة TIFF.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ParagraphFormat.Style = doc.Styles["Heading 1"];
builder.Writeln("Hello world!");
builder.InsertImage(ImageDir + "Logo.jpg");

// عندما نحفظ المستند بتنسيق TIFF ، يمكننا تمرير كائن SaveOptions إليه
// اضبط التردد الذي ستطبقه Aspose.Words عند عرض هذه الصورة.
// القيمة الافتراضية لخاصية "ThresholdForFloydSteinbergDithering" هي 128.
// تميل القيم الأعلى إلى إنتاج صور أكثر قتامة.
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Tiff)
{
    TiffCompression = TiffCompression.Ccitt3,
    TiffBinarizationMethod = ImageBinarizationMethod.FloydSteinbergDithering,
    ThresholdForFloydSteinbergDithering = 240
};

doc.Save(ArtifactsDir + "ImageSaveOptions.FloydSteinbergDithering.tiff", options);
```

### أنظر أيضا

* enum [ImageBinarizationMethod](../../imagebinarizationmethod/)
* class [ImageSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../imagesaveoptions/)
* المجسم [Aspose.Words](../../../)


