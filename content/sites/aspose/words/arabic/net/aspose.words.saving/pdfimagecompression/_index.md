---
title: Enum PdfImageCompression
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Saving.PdfImageCompression تعداد. يحدد نوع الضغط المطبق على الصور في ملف PDF.
type: docs
weight: 5210
url: /ar/net/aspose.words.saving/pdfimagecompression/
---
## PdfImageCompression enumeration

يحدد نوع الضغط المطبق على الصور في ملف PDF.

```csharp
public enum PdfImageCompression
```

### قيم

| اسم | قيمة | وصف |
| --- | --- | --- |
| Auto | `0` | تحديد الضغط الأنسب تلقائيًا لكل صورة. |
| Jpeg | `1` | ضغط Jpeg . لا يدعم الشفافية . |

### أمثلة

يوضح كيفية تحديد نوع الضغط لجميع الصور في المستند الذي نقوم بتحويله إلى PDF.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Jpeg image:");
builder.InsertImage(ImageDir + "Logo.jpg");
builder.InsertParagraph();
builder.Writeln("Png image:");
builder.InsertImage(ImageDir + "Transparent background logo.png");

// قم بإنشاء كائن "PdfSaveOptions" يمكننا تمريره إلى طريقة "Save" الخاصة بالمستند
// لتعديل كيفية تحويل هذه الطريقة المستند إلى PDF.
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();

// اضبط خاصية "ImageCompression" على "PdfImageCompression.Auto" لاستخدام ملف
// "ImageCompression" للتحكم في جودة صور Jpeg التي تنتهي في ملف PDF الناتج.
// اضبط خاصية "ImageCompression" على "PdfImageCompression.Jpeg" لاستخدام ملف
// خاصية ImageCompression للتحكم في جودة كل الصور التي تنتهي في ملف PDF الناتج.
pdfSaveOptions.ImageCompression = pdfImageCompression;

// اضبط خاصية "JpegQuality" على "10" لتقوية الضغط على حساب جودة الصورة.
pdfSaveOptions.JpegQuality = 10;

doc.Save(ArtifactsDir + "PdfSaveOptions.ImageCompression.pdf", pdfSaveOptions);
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words.Saving](../../aspose.words.saving/)
* المجسم [Aspose.Words](../../)


