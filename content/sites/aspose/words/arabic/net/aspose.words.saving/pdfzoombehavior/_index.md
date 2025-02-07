---
title: Enum PdfZoomBehavior
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Saving.PdfZoomBehavior تعداد. يحدد نوع التكبير / التصغير المطبق على مستند PDF عند فتحه في عارض PDF.
type: docs
weight: 5260
url: /ar/net/aspose.words.saving/pdfzoombehavior/
---
## PdfZoomBehavior enumeration

يحدد نوع التكبير / التصغير المطبق على مستند PDF عند فتحه في عارض PDF.

```csharp
public enum PdfZoomBehavior
```

### قيم

| اسم | قيمة | وصف |
| --- | --- | --- |
| None | `0` | تُترك طريقة عرض المستند إلى عارض PDF. عادةً ما يعرض العارض المستند ليلائم عرض الصفحة. |
| ZoomFactor | `1` | يعرض الصفحة باستخدام عامل التكبير المحدد. |
| FitPage | `2` | يعرض الصفحة بحيث تكون مرئية بالكامل . |
| FitWidth | `3` | يناسب عرض الصفحة. |
| FitHeight | `4` | يناسب ارتفاع الصفحة. |
| FitBox | `5` | يناسب المربع المحيط (مستطيل يحتوي على جميع العناصر المرئية في الصفحة). |

### أمثلة

يوضح كيفية تعيين التكبير الافتراضي الذي يطبقه القارئ عند فتح مستند PDF مقدم.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

// قم بإنشاء كائن "PdfSaveOptions" يمكننا تمريره إلى طريقة "Save" الخاصة بالمستند
// لتعديل كيفية تحويل هذه الطريقة المستند إلى PDF.
// قم بتعيين خاصية "ZoomBehavior" على "PdfZoomBehavior.ZoomFactor" للحصول على قارئ PDF
// قم بتطبيق عامل تكبير على أساس النسبة المئوية عندما نفتح المستند به.
// اضبط خاصية "ZoomFactor" على "25" لمنح عامل التكبير / التصغير قيمة 25٪.
PdfSaveOptions options = new PdfSaveOptions
{
    ZoomBehavior = PdfZoomBehavior.ZoomFactor,
    ZoomFactor = 25
};

// عندما نفتح هذا المستند باستخدام قارئ مثل Adobe Acrobat ، سنرى المستند بحجم 1/4 من حجمه الفعلي.
doc.Save(ArtifactsDir + "PdfSaveOptions.ZoomBehaviour.pdf", options);
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words.Saving](../../aspose.words.saving/)
* المجسم [Aspose.Words](../../)


