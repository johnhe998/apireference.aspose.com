---
title: Enum EmfPlusDualRenderingMode
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Saving.EmfPlusDualRenderingMode تعداد. يحدد كيف يجب على Aspose.Words عرض EMF  Dual metafiles .
type: docs
weight: 4720
url: /ar/net/aspose.words.saving/emfplusdualrenderingmode/
---
## EmfPlusDualRenderingMode enumeration

يحدد كيف يجب على Aspose.Words عرض EMF + Dual metafiles .

```csharp
public enum EmfPlusDualRenderingMode
```

### قيم

| اسم | قيمة | وصف |
| --- | --- | --- |
| EmfPlusWithFallback | `0` | Aspose.Words يحاول تقديم EMF + جزء من EMF + Dual metafile. إذا كانت بعض سجلات EMF + غير مدعومة فإن Aspose.Words يعرض جزء EMF من EMF + Dual metafile . |
| EmfPlus | `1` | Aspose.Words يجعل EMF + جزء من EMF + ملف تعريف مزدوج . |
| Emf | `2` | Aspose.Words يجعل جزء EMF من EMF + Dual metafile . |

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

* مساحة الاسم [Aspose.Words.Saving](../../aspose.words.saving/)
* المجسم [Aspose.Words](../../)


