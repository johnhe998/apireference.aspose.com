---
title: SaveOptions.DmlRenderingMode
second_title: Aspose.Words لمراجع .NET API
description: SaveOptions ملكية. الحصول على قيمة أو تعيينها لتحديد كيفية عرض أشكال DrawingML .
type: docs
weight: 70
url: /ar/net/aspose.words.saving/saveoptions/dmlrenderingmode/
---
## SaveOptions.DmlRenderingMode property

الحصول على قيمة أو تعيينها لتحديد كيفية عرض أشكال DrawingML .

```csharp
public DmlRenderingMode DmlRenderingMode { get; set; }
```

### ملاحظات

القيمة الافتراضية هيFallback .

يتم استخدام هذه الخاصية عند تصدير الوثيقة إلى تنسيقات الصفحات الثابتة.

### أمثلة

يوضح كيفية عرض الأشكال الاحتياطية عند الحفظ في PDF.

```csharp
Document doc = new Document(MyDir + "DrawingML shape fallbacks.docx");

// قم بإنشاء كائن "PdfSaveOptions" يمكننا تمريره إلى طريقة "Save" الخاصة بالمستند
// لتعديل كيفية تحويل هذه الطريقة المستند إلى PDF.
PdfSaveOptions options = new PdfSaveOptions();

// تعيين خاصية "DmlRenderingMode" على "DmlRenderingMode.Fallback"
// لاستبدال أشكال DML بأشكالها الاحتياطية.
// تعيين خاصية "DmlRenderingMode" على "DmlRenderingMode.DrawingML"
// لتقديم أشكال DML نفسها.
options.DmlRenderingMode = dmlRenderingMode;

doc.Save(ArtifactsDir + "PdfSaveOptions.DrawingMLFallback.pdf", options);
```

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

* enum [DmlRenderingMode](../../dmlrenderingmode/)
* class [SaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../saveoptions/)
* المجسم [Aspose.Words](../../../)


