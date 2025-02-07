---
title: Enum DmlEffectsRenderingMode
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Saving.DmlEffectsRenderingMode تعداد. يحدد كيفية عرض تأثيرات DrawingML على تنسيقات الصفحة الثابتة.
type: docs
weight: 4650
url: /ar/net/aspose.words.saving/dmleffectsrenderingmode/
---
## DmlEffectsRenderingMode enumeration

يحدد كيفية عرض تأثيرات DrawingML على تنسيقات الصفحة الثابتة.

```csharp
public enum DmlEffectsRenderingMode
```

### قيم

| اسم | قيمة | وصف |
| --- | --- | --- |
| Simplified | `0` | عرض تأثيرات DrawingML مبسطة . |
| None | `1` | لا يتم تقديم تأثيرات DrawingML . |
| Fine | `2` | يتم تقديم تأثيرات DrawingML في الوضع الدقيق الذي يتضمن معالجة متقدمة . في هذا الوضع ، يعطي عرض التأثيرات نتائج أفضل ولكن بتكلفة أداء أعلى منSimplified الوضع . |

### أمثلة

يوضح كيفية تكوين جودة العرض لتأثيرات DrawingML في مستند أثناء حفظه في PDF.

```csharp
Document doc = new Document(MyDir + "DrawingML shape effects.docx");

// قم بإنشاء كائن "PdfSaveOptions" يمكننا تمريره إلى طريقة "Save" الخاصة بالمستند
// لتعديل كيفية تحويل هذه الطريقة المستند إلى PDF.
PdfSaveOptions options = new PdfSaveOptions();

// قم بتعيين خاصية "DmlEffectsRenderingMode" على "DmlEffectsRenderingMode.None" لتجاهل كافة تأثيرات DrawingML.
// تعيين خاصية "DmlEffectsRenderingMode" على "DmlEffectsRenderingMode.Simplified"
// لتقديم نسخة مبسطة من تأثيرات DrawingML.
// قم بتعيين خاصية "DmlEffectsRenderingMode" على "DmlEffectsRenderingMode.Fine" إلى
// تقديم تأثيرات DrawingML بمزيد من الدقة وأيضًا بتكلفة معالجة أكبر.
options.DmlEffectsRenderingMode = effectsRenderingMode;

Assert.AreEqual(DmlRenderingMode.DrawingML, options.DmlRenderingMode);

doc.Save(ArtifactsDir + "PdfSaveOptions.DrawingMLEffects.pdf", options);
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words.Saving](../../aspose.words.saving/)
* المجسم [Aspose.Words](../../)


