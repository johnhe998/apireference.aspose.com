---
title: Enum ImageBinarizationMethod
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Saving.ImageBinarizationMethod تعداد. يحدد الطريقة المستخدمة لترتيب الصورة بالترميز الثنائي .
type: docs
weight: 4940
url: /ar/net/aspose.words.saving/imagebinarizationmethod/
---
## ImageBinarizationMethod enumeration

يحدد الطريقة المستخدمة لترتيب الصورة بالترميز الثنائي .

```csharp
public enum ImageBinarizationMethod
```

### قيم

| اسم | قيمة | وصف |
| --- | --- | --- |
| Threshold | `0` | يحدد طريقة العتبة . |
| FloydSteinbergDithering | `1` | يحدد ثبات الألوان باستخدام طريقة Floyd-Steinberg لنشر الخطأ. |

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

* مساحة الاسم [Aspose.Words.Saving](../../aspose.words.saving/)
* المجسم [Aspose.Words](../../)


