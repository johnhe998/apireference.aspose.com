---
title: HtmlFixedSaveOptions.OptimizeOutput
second_title: Aspose.Words لمراجع .NET API
description: HtmlFixedSaveOptions ملكية. تشير العلامة إلى ما إذا كان مطلوبًا لتحسين الإخراج. إذا تم تعيين هذه العلامة قماشية متداخلة متكررة وتمت إزالة اللوحات الفارغة  يتم أيضًا ربط الحروف الرسومية المجاورة بنفس التنسيق . ملاحظة قد تتأثر دقة عرض المحتوى إذا تم تعيين هذه الخاصية على true . القيمة الافتراضية هي true .
type: docs
weight: 100
url: /ar/net/aspose.words.saving/htmlfixedsaveoptions/optimizeoutput/
---
## HtmlFixedSaveOptions.OptimizeOutput property

تشير العلامة إلى ما إذا كان مطلوبًا لتحسين الإخراج. إذا تم تعيين هذه العلامة قماشية متداخلة متكررة وتمت إزالة اللوحات الفارغة ، يتم أيضًا ربط الحروف الرسومية المجاورة بنفس التنسيق . ملاحظة: قد تتأثر دقة عرض المحتوى إذا تم تعيين هذه الخاصية على true . القيمة الافتراضية هي true .

```csharp
public override bool OptimizeOutput { get; set; }
```

### أمثلة

يوضح كيفية تبسيط مستند عند حفظه في HTML عن طريق إزالة العديد من الكائنات المكررة.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { OptimizeOutput = optimizeOutput };

doc.Save(ArtifactsDir + "HtmlFixedSaveOptions.OptimizeGraphicsOutput.html", saveOptions);

// حجم النسخة المحسّنة من المستند تقريبًا ثلث حجم المستند غير المحسّن.
Assert.AreEqual(optimizeOutput ? 62521 : 191770,
    new FileInfo(ArtifactsDir + "HtmlFixedSaveOptions.OptimizeGraphicsOutput.html").Length, 200);
```

### أنظر أيضا

* class [HtmlFixedSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../htmlfixedsaveoptions/)
* المجسم [Aspose.Words](../../../)


