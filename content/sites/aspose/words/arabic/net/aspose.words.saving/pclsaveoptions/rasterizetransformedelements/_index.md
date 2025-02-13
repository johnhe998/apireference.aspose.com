---
title: PclSaveOptions.RasterizeTransformedElements
second_title: Aspose.Words لمراجع .NET API
description: PclSaveOptions ملكية. الحصول على أو تعيين قيمة تحدد ما إذا كانت العناصر المحولة المعقدة يجب تنقيطها قبل الحفظ في مستند PCL . الإعداد الافتراضي هوحقيقي .
type: docs
weight: 30
url: /ar/net/aspose.words.saving/pclsaveoptions/rasterizetransformedelements/
---
## PclSaveOptions.RasterizeTransformedElements property

الحصول على أو تعيين قيمة تحدد ما إذا كانت العناصر المحولة المعقدة يجب تنقيطها قبل الحفظ في مستند PCL . الإعداد الافتراضي هو`حقيقي` .

```csharp
public bool RasterizeTransformedElements { get; set; }
```

### ملاحظات

لا تدعم PCL نوعًا من التحويلات التي تستخدمها Aspose Words . على سبيل المثال ، الصور المستديرة والمنحرفة وفرش النسيج. لتصيير هذه العناصر يتم استخدام عملية التنقيط بشكل صحيح ، أي الحفظ على الصورة والقص . يمكن أن تستغرق هذه العملية وقتًا وذاكرة إضافية.`خاطئة`، قد يكون بعض المحتوى في المخرجات مختلفًا مقارنة بالمستند المصدر.

### أمثلة

يوضح كيفية تنقيط العناصر المعقدة أثناء حفظ مستند في PCL.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

PclSaveOptions saveOptions = new PclSaveOptions
{
    SaveFormat = SaveFormat.Pcl,
    RasterizeTransformedElements = true
};

doc.Save(ArtifactsDir + "PclSaveOptions.RasterizeElements.pcl", saveOptions);
```

### أنظر أيضا

* class [PclSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../pclsaveoptions/)
* المجسم [Aspose.Words](../../../)


