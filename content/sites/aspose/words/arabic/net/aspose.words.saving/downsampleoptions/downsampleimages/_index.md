---
title: DownsampleOptions.DownsampleImages
second_title: Aspose.Words لمراجع .NET API
description: DownsampleOptions ملكية. يحدد ما إذا كان يجب اختزال حجم الصور.
type: docs
weight: 20
url: /ar/net/aspose.words.saving/downsampleoptions/downsampleimages/
---
## DownsampleOptions.DownsampleImages property

يحدد ما إذا كان يجب اختزال حجم الصور.

```csharp
public bool DownsampleImages { get; set; }
```

### ملاحظات

القيمة الافتراضية هي`حقيقي` .

### أمثلة

يوضح كيفية تغيير دقة الصور في مستند PDF.

```csharp
Document doc = new Document(MyDir + "Images.docx");

// قم بإنشاء كائن "PdfSaveOptions" يمكننا تمريره إلى طريقة "Save" الخاصة بالمستند
// لتعديل كيفية تحويل هذه الطريقة المستند إلى PDF.
PdfSaveOptions options = new PdfSaveOptions();

// بشكل افتراضي ، تختزل Aspose.Words جميع الصور في مستند نقوم بحفظه في PDF إلى 220 نقطة في البوصة.
Assert.True(options.DownsampleOptions.DownsampleImages);
Assert.AreEqual(220, options.DownsampleOptions.Resolution);
Assert.AreEqual(0, options.DownsampleOptions.ResolutionThreshold);

doc.Save(ArtifactsDir + "PdfSaveOptions.DownsampleOptions.Default.pdf", options);

// اضبط خاصية "Resolution" على "36" لاختزال جميع الصور إلى 36 نقطة في البوصة.
options.DownsampleOptions.Resolution = 36;

// قم بتعيين خاصية "ResolutionThreshold" لتطبيق الاختزال فقط على
// الصور بدقة أعلى من 128 نقطة في البوصة.
options.DownsampleOptions.ResolutionThreshold = 128;

// سيتم تصغير الصورتين الأوليين فقط من المستند في هذه المرحلة.
doc.Save(ArtifactsDir + "PdfSaveOptions.DownsampleOptions.LowerResolution.pdf", options);
```

### أنظر أيضا

* class [DownsampleOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../downsampleoptions/)
* المجسم [Aspose.Words](../../../)


