---
title: PdfSaveOptions.ExportLanguageToSpanTag
second_title: Aspose.Words لمراجع .NET API
description: PdfSaveOptions ملكية. الحصول على أو تعيين قيمة تحدد ما إذا كان سيتم إنشاء علامة امتداد في بنية المستند لتصدير لغة النص أم لا.
type: docs
weight: 130
url: /ar/net/aspose.words.saving/pdfsaveoptions/exportlanguagetospantag/
---
## PdfSaveOptions.ExportLanguageToSpanTag property

الحصول على أو تعيين قيمة تحدد ما إذا كان سيتم إنشاء علامة "امتداد" في بنية المستند لتصدير لغة النص أم لا.

```csharp
public bool ExportLanguageToSpanTag { get; set; }
```

### ملاحظات

القيمة الافتراضية هي`خاطئة` والسمة "Lang" مرفقة بتسلسل محتوى محدد في تدفق محتوى الصفحة.

عندما تكون القيمة`حقيقي` يتم إنشاء علامة "Span" للنص الذي يحتوي على لغة غير افتراضية ويتم إرفاق سمة "Lang" بهذه العلامة.

يتم تجاهل هذه القيمة عندما[`ExportDocumentStructure`](../exportdocumentstructure/) هو`خاطئة` .

### أمثلة

يوضح كيفية إنشاء علامة "Span" في بنية المستند لتصدير لغة النص.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Hello world!");
builder.Writeln("Hola mundo!");

PdfSaveOptions saveOptions = new PdfSaveOptions
{
    // ملاحظة ، عندما تكون "ExportDocumentStructure" خاطئة ، يتم تجاهل "ExportLanguageToSpanTag".
    ExportDocumentStructure = true, ExportLanguageToSpanTag = true
};

doc.Save(ArtifactsDir + "PdfSaveOptions.ExportLanguageToSpanTag.pdf", saveOptions);
```

### أنظر أيضا

* class [PdfSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../pdfsaveoptions/)
* المجسم [Aspose.Words](../../../)


