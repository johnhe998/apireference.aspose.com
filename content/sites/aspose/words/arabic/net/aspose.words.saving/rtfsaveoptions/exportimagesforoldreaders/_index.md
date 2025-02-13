---
title: RtfSaveOptions.ExportImagesForOldReaders
second_title: Aspose.Words لمراجع .NET API
description: RtfSaveOptions ملكية. يحدد ما إذا كانت الكلمات الأساسية لـ القراء القدامى مكتوبة على RTF أم لا. يمكن أن يؤثر هذا بشكل كبير على حجم مستند RTF. القيمة الافتراضية هيحقيقي .
type: docs
weight: 30
url: /ar/net/aspose.words.saving/rtfsaveoptions/exportimagesforoldreaders/
---
## RtfSaveOptions.ExportImagesForOldReaders property

يحدد ما إذا كانت الكلمات الأساسية لـ "القراء القدامى" مكتوبة على RTF أم لا. يمكن أن يؤثر هذا بشكل كبير على حجم مستند RTF. القيمة الافتراضية هي`حقيقي` .

```csharp
public bool ExportImagesForOldReaders { get; set; }
```

### ملاحظات

"القراء القدامى" هم تطبيقات ما قبل Microsoft Word 97 وكذلك الدفتر . عندما يكون هذا الخيار`حقيقي` يكتب Aspose.Words كلمات رئيسية إضافية لـ RTF . تسمح هذه الكلمات الرئيسية بعرض المستند بشكل صحيح عند فتحه في تطبيق "قارئ قديم" ، ولكن يمكن أن يزيد حجم المستند بشكل ملحوظ.

إذا قمت بتعيين هذا الخيار على`خاطئة`، فلن يتم عرض سوى الصور بتنسيقات WMF و EMF و BMP في "أجهزة القراءة القديمة".

### أمثلة

يوضح كيفية حفظ مستند في .rtf بخيارات مخصصة.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// قم بإنشاء كائن "RtfSaveOptions" لتمريره إلى أسلوب "Save" الخاص بالمستند لتعديل كيفية حفظه في RTF.
RtfSaveOptions options = new RtfSaveOptions();

Assert.AreEqual(SaveFormat.Rtf, options.SaveFormat);

// اضبط خاصية "ExportCompactSize" على "true" إلى
// تقليل حجم المستند المحفوظ على حساب توافق النص من اليمين إلى اليسار.
options.ExportCompactSize = true;

// اضبط خاصية "ExportImagesFotOldReaders" على "true" لاستخدام كلمات رئيسية إضافية للتأكد من أن وثيقتنا
// متوافق مع أجهزة قراءة ما قبل Microsoft Word 97 و WordPad.
// اضبط خاصية "ExportImagesFotOldReaders" على "خطأ" لتقليل حجم المستند ،
// ولكن تمنع القراء القدامى من قراءة أي صور غير ملفات تعريف أو صور BMP قد يحتوي عليها المستند.
options.ExportImagesForOldReaders = exportImagesForOldReaders;

doc.Save(ArtifactsDir + "RtfSaveOptions.ExportImages.rtf", options);
```

### أنظر أيضا

* class [RtfSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../rtfsaveoptions/)
* المجسم [Aspose.Words](../../../)


