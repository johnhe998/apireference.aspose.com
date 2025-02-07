---
title: PdfSaveOptions.TextCompression
second_title: Aspose.Words لمراجع .NET API
description: PdfSaveOptions ملكية. يحدد نوع الضغط الذي سيتم استخدامه لجميع المحتويات النصية في المستند.
type: docs
weight: 260
url: /ar/net/aspose.words.saving/pdfsaveoptions/textcompression/
---
## PdfSaveOptions.TextCompression property

يحدد نوع الضغط الذي سيتم استخدامه لجميع المحتويات النصية في المستند.

```csharp
public PdfTextCompression TextCompression { get; set; }
```

### ملاحظات

الافتراضي هوFlate.

يزيد حجم الإخراج بشكل كبير عند حفظ مستند بدون ضغط.

### أمثلة

يوضح كيفية تطبيق ضغط النص عند حفظ مستند في PDF.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

for (int i = 0; i < 100; i++)
    builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, " +
                    "sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");

// قم بإنشاء كائن "PdfSaveOptions" يمكننا تمريره إلى طريقة "Save" الخاصة بالمستند
// لتعديل كيفية تحويل هذه الطريقة المستند إلى PDF.
PdfSaveOptions options = new PdfSaveOptions();

// اضبط خاصية "TextCompression" على "PdfTextCompression.None" لعدم تطبيق أي منها
// الضغط على النص عندما نحفظ المستند في PDF.
// اضبط خاصية "TextCompression" على "PdfTextCompression.Flate" لتطبيق ضغط ZIP
// إلى النص عندما نحفظ المستند في PDF. كلما زاد حجم المستند ، زاد تأثير ذلك.
options.TextCompression = pdfTextCompression;

doc.Save(ArtifactsDir + "PdfSaveOptions.TextCompression.pdf", options);
```

### أنظر أيضا

* enum [PdfTextCompression](../../pdftextcompression/)
* class [PdfSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../pdfsaveoptions/)
* المجسم [Aspose.Words](../../../)


