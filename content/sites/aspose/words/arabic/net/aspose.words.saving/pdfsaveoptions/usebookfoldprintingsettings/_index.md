---
title: PdfSaveOptions.UseBookFoldPrintingSettings
second_title: Aspose.Words لمراجع .NET API
description: PdfSaveOptions ملكية. الحصول على أو تعيين قيمة منطقية تشير إلى ما إذا كان يجب حفظ المستند باستخدام تخطيط طباعة كتيب  إذا تم تحديده عبرMultiplePages .
type: docs
weight: 270
url: /ar/net/aspose.words.saving/pdfsaveoptions/usebookfoldprintingsettings/
---
## PdfSaveOptions.UseBookFoldPrintingSettings property

الحصول على أو تعيين قيمة منطقية تشير إلى ما إذا كان يجب حفظ المستند باستخدام تخطيط طباعة كتيب ، إذا تم تحديده عبر[`MultiplePages`](../../../aspose.words/pagesetup/multiplepages/) .

```csharp
public bool UseBookFoldPrintingSettings { get; set; }
```

### ملاحظات

إذا تم تحديد هذا الخيار ،[`PageSet`](../../fixedpagesaveoptions/pageset/) يتم تجاهلها عند الحفظ.

### أمثلة

يوضح كيفية حفظ مستند بتنسيق PDF في شكل طية كتاب.

```csharp
Document doc = new Document(MyDir + "Paragraphs.docx");

// قم بإنشاء كائن "PdfSaveOptions" يمكننا تمريره إلى طريقة "Save" الخاصة بالمستند
// لتعديل كيفية تحويل هذه الطريقة المستند إلى PDF.
PdfSaveOptions options = new PdfSaveOptions();

// اضبط خاصية "UseBookFoldPrintingSettings" على "true" لترتيب المحتويات
// في ملف PDF الناتج بطريقة تساعدنا في استخدامه لعمل كتيب.
// اضبط خاصية "UseBookFoldPrintingSettings" على "false" لعرض ملف PDF بشكل طبيعي.
options.UseBookFoldPrintingSettings = renderTextAsBookfold;

// إذا كنا نقدم المستند ككتيب ، فيجب علينا تعيين "صفحات متعددة"
// خصائص كائنات إعداد الصفحة لجميع الأقسام إلى "MultiplePagesType.BookFoldPrinting".
if (renderTextAsBookfold)
    foreach (Section s in doc.Sections)
    {
        s.PageSetup.MultiplePages = MultiplePagesType.BookFoldPrinting;
    }

// بمجرد طباعة هذا المستند على كلا وجهي الصفحات ، يمكننا طي جميع الصفحات لأسفل في المنتصف مرة واحدة ،
// وستصطف المحتويات بطريقة تؤدي إلى إنشاء كتيب.
doc.Save(ArtifactsDir + "PdfSaveOptions.SaveAsPdfBookFold.pdf", options);
```

### أنظر أيضا

* class [PdfSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../pdfsaveoptions/)
* المجسم [Aspose.Words](../../../)


