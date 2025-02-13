---
title: HtmlSaveOptions.ExportPageSetup
second_title: Aspose.Words لمراجع .NET API
description: HtmlSaveOptions ملكية. يحدد ما إذا كان إعداد الصفحة سيتم تصديره إلى HTML أو MHTML أو EPUB. الإعداد الافتراضي هوخاطئة .
type: docs
weight: 230
url: /ar/net/aspose.words.saving/htmlsaveoptions/exportpagesetup/
---
## HtmlSaveOptions.ExportPageSetup property

يحدد ما إذا كان إعداد الصفحة سيتم تصديره إلى HTML أو MHTML أو EPUB. الإعداد الافتراضي هو`خاطئة` .

```csharp
public bool ExportPageSetup { get; set; }
```

### ملاحظات

كل[`Section`](../../../aspose.words/section/) في نموذج مستند Aspose.Words يوفر معلومات إعداد الصفحة عبر[`PageSetup`](../../../aspose.words/pagesetup/) صف دراسي. عند تصدير مستند إلى تنسيق HTML ، قد تحتاج إلى الاحتفاظ بهذه المعلومات_ لمزيد من الاستخدام. على وجه الخصوص ، قد يكون إعداد الصفحة مهمًا للعرض على الوسائط المقسمة إلى صفحات (طباعة) أو التحويل اللاحق إلى تنسيقات ملفات Microsoft Word الأصلية (DOCX ، DOC ، RTF ، WML).

في معظم الحالات ، يكون HTML مخصصًا للعرض في المتصفحات التي لا يتم فيها ترقيم الصفحات. لذلك فإن هذه feature غير نشطة بشكل افتراضي.

### أمثلة

يوضح كيفية تحديد ما إذا كان سيتم الاحتفاظ بهيكل القسم / معلومات إعداد الصفحة عند الحفظ بتنسيق HTML.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Section 1");
builder.InsertBreak(BreakType.SectionBreakNewPage);
builder.Write("Section 2");

PageSetup pageSetup = doc.Sections[0].PageSetup;
pageSetup.TopMargin = 36.0;
pageSetup.BottomMargin = 36.0;
pageSetup.PaperSize = PaperSize.A5;

// عند حفظ المستند إلى HTML ، يمكننا تمرير كائن SaveOptions
// لتقرر ما إذا كنت تريد الاحتفاظ بإعدادات إعداد الصفحة أو تجاهلها.
// إذا قمنا بتعيين علامة "ExportPageSetup" على "true" ، فسيحتوي مستند HTML الناتج على تكوين إعداد الصفحة الخاص بنا.
// إذا قمنا بتعيين علامة "ExportPageSetup" على "خطأ" ، فستتجاهل عملية الحفظ إعدادات إعداد الصفحة الخاصة بنا
// للقسم الأول ، وسيبدو كلا القسمين متطابقين.
HtmlSaveOptions options = new HtmlSaveOptions { ExportPageSetup = exportPageSetup };

doc.Save(ArtifactsDir + "HtmlSaveOptions.ExportPageSetup.html", options);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlSaveOptions.ExportPageSetup.html");

if (exportPageSetup)
{
    Assert.True(outDocContents.Contains(
        "<style type=\"text/css\">" +
            "@page Section1 { size:419.55pt 595.3pt; margin:36pt 70.85pt }" +
            "@page Section2 { size:612pt 792pt; margin:70.85pt }" +
            "div.Section1 { page:Section1 }div.Section2 { page:Section2 }" +
        "</style>"));

    Assert.True(outDocContents.Contains(
        "<div class=\"Section1\">" +
            "<p style=\"margin-top:0pt; margin-bottom:0pt\">" +
                "<span>Section 1</span>" +
            "</p>" +
        "</div>"));
}
else
{
    Assert.False(outDocContents.Contains("style type=\"text/css\">"));

    Assert.True(outDocContents.Contains(
        "<div>" +
            "<p style=\"margin-top:0pt; margin-bottom:0pt\">" +
                "<span>Section 1</span>" +
            "</p>" +
        "</div>"));
}
```

### أنظر أيضا

* class [HtmlSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../htmlsaveoptions/)
* المجسم [Aspose.Words](../../../)


