---
title: PdfSaveOptions.AdditionalTextPositioning
second_title: Aspose.Words لمراجع .NET API
description: PdfSaveOptions ملكية. علامة تحدد ما إذا كنت تريد كتابة عوامل تحديد مواقع نصية إضافية أم لا.
type: docs
weight: 20
url: /ar/net/aspose.words.saving/pdfsaveoptions/additionaltextpositioning/
---
## PdfSaveOptions.AdditionalTextPositioning property

علامة تحدد ما إذا كنت تريد كتابة عوامل تحديد مواقع نصية إضافية أم لا.

```csharp
public bool AdditionalTextPositioning { get; set; }
```

### ملاحظات

إذا`حقيقي` ، تتم كتابة عوامل تحديد مواقع النص الإضافية في ملف PDF الناتج. قد يساعد هذا في التغلب على المشكلات المتعلقة بتحديد موضع النص غير الدقيق في بعض الطابعات. الجانب السلبي هو زيادة حجم مستند PDF.

النظام الأساسي`خاطئة`.

### أمثلة

أظهر كيفية كتابة عوامل تحديد موضع النص الإضافية.

```csharp
Document doc = new Document(MyDir + "Text positioning operators.docx");

// قم بإنشاء كائن "PdfSaveOptions" يمكننا تمريره إلى طريقة "Save" الخاصة بالمستند
// لتعديل كيفية تحويل هذه الطريقة المستند إلى PDF.
PdfSaveOptions saveOptions = new PdfSaveOptions
{
    TextCompression = PdfTextCompression.None,

    // قم بتعيين خاصية "AdditionalTextPositioning" إلى "true" لمحاولة إصلاح الخطأ
    // وضع العنصر في ملف PDF الناتج ، إذا كان هناك أي شيء ، على حساب زيادة حجم الملف.
    // اضبط خاصية "AdditionalTextPositioning" على "false" لتقديم المستند كالمعتاد.
    AdditionalTextPositioning = applyAdditionalTextPositioning
};

doc.Save(ArtifactsDir + "PdfSaveOptions.AdditionalTextPositioning.pdf", saveOptions);
```

### أنظر أيضا

* class [PdfSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../pdfsaveoptions/)
* المجسم [Aspose.Words](../../../)


