---
title: PdfSaveOptions.CreateNoteHyperlinks
second_title: Aspose.Words لمراجع .NET API
description: PdfSaveOptions ملكية. يحدد ما إذا كان سيتم تحويل مراجع الحواشي السفلية / التعليقات الختامية في القصة النصية الرئيسية إلى ارتباطات تشعبية نشطة.خاطئة .
type: docs
weight: 40
url: /ar/net/aspose.words.saving/pdfsaveoptions/createnotehyperlinks/
---
## PdfSaveOptions.CreateNoteHyperlinks property

يحدد ما إذا كان سيتم تحويل مراجع الحواشي السفلية / التعليقات الختامية في القصة النصية الرئيسية إلى ارتباطات تشعبية نشطة.`خاطئة` .

```csharp
public bool CreateNoteHyperlinks { get; set; }
```

### أمثلة

يوضح كيفية جعل الحواشي السفلية والتعليقات الختامية تعمل كارتباطات تشعبية.

```csharp
Document doc = new Document(MyDir + "Footnotes and endnotes.docx");

// قم بإنشاء كائن "PdfSaveOptions" يمكننا تمريره إلى طريقة "Save" الخاصة بالمستند
// لتعديل كيفية تحويل هذه الطريقة المستند إلى PDF.
PdfSaveOptions options = new PdfSaveOptions();

// قم بتعيين خاصية "CreateNoteHyperlinks" على "true" لتحويل جميع رموز الحواشي السفلية / التعليقات الختامية
// في النص بمثابة روابط تأخذنا ، عند النقر ، إلى الحواشي السفلية / التعليقات الختامية الخاصة بكل منها.
// اضبط خاصية "CreateNoteHyperlinks" على "false" حتى لا ترتبط رموز الحواشي السفلية / التعليقات الختامية بأي شيء.
options.CreateNoteHyperlinks = createNoteHyperlinks;

doc.Save(ArtifactsDir + "PdfSaveOptions.NoteHyperlinks.pdf", options);
```

### أنظر أيضا

* class [PdfSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../pdfsaveoptions/)
* المجسم [Aspose.Words](../../../)


