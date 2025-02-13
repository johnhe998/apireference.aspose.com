---
title: MetafileRenderingOptions.UseEmfEmbeddedToWmf
second_title: Aspose.Words لمراجع .NET API
description: MetafileRenderingOptions ملكية. الحصول على أو تعيين قيمة تحدد كيفية عرض ملفات تعريف WMF مع ملفات تعريف EMF المضمنة.
type: docs
weight: 60
url: /ar/net/aspose.words.saving/metafilerenderingoptions/useemfembeddedtowmf/
---
## MetafileRenderingOptions.UseEmfEmbeddedToWmf property

الحصول على أو تعيين قيمة تحدد كيفية عرض ملفات تعريف WMF مع ملفات تعريف EMF المضمنة.

```csharp
public bool UseEmfEmbeddedToWmf { get; set; }
```

### ملاحظات

يمكن أن تحتوي ملفات تعريف WMF على بيانات EMF مضمنة. يستخدم MS Word في معظم الحالات بيانات EMF المضمنة . يستخدم GDI + دائمًا بيانات WMF.

عندما يتم تعيين هذه القيمة على`حقيقي`يستخدم Aspose.Words بيانات EMF المضمنة عند العرض.

عندما يتم تعيين هذه القيمة على`خاطئة`يستخدم Aspose.Words بيانات WMF عند العرض.

يتم استخدام هذا الخيار فقط عندما يتم تقديم ملف التعريف كرسومات متجهة. عندما يتم تقديم ملف تعريف إلى صورة نقطية ، يتم استخدام بيانات WMF دائمًا.

النظام الأساسي`حقيقي`.

### أمثلة

يوضح كيفية تكوين خيارات العرض ذات الصلة بملف تعريف Windows المحسن عند الحفظ في ملف PDF.

```csharp
Document doc = new Document(MyDir + "EMF.docx");

// قم بإنشاء كائن "PdfSaveOptions" يمكننا تمريره إلى طريقة "Save" الخاصة بالمستند
// لتعديل كيفية تحويل هذه الطريقة المستند إلى PDF.
PdfSaveOptions saveOptions = new PdfSaveOptions();

// تعيين خاصية "EmfPlusDualRenderingMode" على "EmfPlusDualRenderingMode.Emf"
// لعرض جزء EMF من ملف تعريف EMF + مزدوج فقط.
// قم بتعيين خاصية "EmfPlusDualRenderingMode" على "EmfPlusDualRenderingMode.EmfPlus" إلى
// لتقديم EMF + جزء من ملف تعريف EMF + مزدوج.
// قم بتعيين خاصية "EmfPlusDualRenderingMode" على "EmfPlusDualRenderingMode.EmfPlusWithFallback"
// لتقديم EMF + جزء من ملف تعريف EMF + مزدوج إذا كانت جميع سجلات EMF + مدعومة.
// خلاف ذلك ، ستعرض Aspose.Words جزء EMF.
saveOptions.MetafileRenderingOptions.EmfPlusDualRenderingMode = renderingMode;

// اضبط خاصية "UseEmfEmbeddedToWmf" على "true" لعرض بيانات EMF المضمنة
// لملفات التعريف التي يمكننا تقديمها كرسومات متجهة.
saveOptions.MetafileRenderingOptions.UseEmfEmbeddedToWmf = true;

doc.Save(ArtifactsDir + "PdfSaveOptions.RenderMetafile.pdf", saveOptions);
```

### أنظر أيضا

* class [MetafileRenderingOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../metafilerenderingoptions/)
* المجسم [Aspose.Words](../../../)


