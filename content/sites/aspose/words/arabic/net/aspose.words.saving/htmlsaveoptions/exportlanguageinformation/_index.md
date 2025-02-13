---
title: HtmlSaveOptions.ExportLanguageInformation
second_title: Aspose.Words لمراجع .NET API
description: HtmlSaveOptions ملكية. يحدد ما إذا كان سيتم تصدير معلومات اللغة إلى HTML أو MHTML أو EPUB. الافتراضي هوخاطئة .
type: docs
weight: 190
url: /ar/net/aspose.words.saving/htmlsaveoptions/exportlanguageinformation/
---
## HtmlSaveOptions.ExportLanguageInformation property

يحدد ما إذا كان سيتم تصدير معلومات اللغة إلى HTML أو MHTML أو EPUB. الافتراضي هو`خاطئة` .

```csharp
public bool ExportLanguageInformation { get; set; }
```

### ملاحظات

عندما يتم تعيين هذه الخاصية على`حقيقي` مخرجات Aspose.Words **لانج** سمة HTML في عناصر document التي تحدد اللغة. يمكن أن يكون هذا ضروريًا للحفاظ على الدلالات اللغوية ذات الصلة.

### أمثلة

يوضح كيفية الحفاظ على معلومات اللغة عند الحفظ في .html.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// استخدم المنشئ لكتابة نص أثناء تنسيقه بلغات مختلفة.
builder.Font.LocaleId = new CultureInfo("en-US").LCID;
builder.Writeln("Hello world!");

builder.Font.LocaleId = new CultureInfo("en-GB").LCID;
builder.Writeln("Hello again!");

builder.Font.LocaleId = new CultureInfo("ru-RU").LCID;
builder.Write("Привет, мир!");

// عند حفظ المستند إلى HTML ، يمكننا تمرير كائن SaveOptions
// إما للاحتفاظ أو تجاهل الإعدادات المحلية لكل نص منسق.
// إذا قمنا بتعيين علامة "ExportLanguageInformation" على "true" ،
// سيحتوي مستند HTML الناتج على اللغات في سمات "lang" لـ < span > العلامات.
// إذا قمنا بتعيين علامة "ExportLanguageInformation" على "خطأ" ،
// لن يحتوي النص الموجود في مستند HTML الناتج على أية معلومات محلية.
HtmlSaveOptions options = new HtmlSaveOptions
{
    ExportLanguageInformation = exportLanguageInformation,
    PrettyFormat = true
};

doc.Save(ArtifactsDir + "HtmlSaveOptions.ExportLanguageInformation.html", options);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlSaveOptions.ExportLanguageInformation.html");

if (exportLanguageInformation)
{
    Assert.True(outDocContents.Contains("<span>Hello world!</span>"));
    Assert.True(outDocContents.Contains("<span lang=\"en-GB\">Hello again!</span>"));
    Assert.True(outDocContents.Contains("<span lang=\"ru-RU\">Привет, мир!</span>"));
}
else
{
    Assert.True(outDocContents.Contains("<span>Hello world!</span>"));
    Assert.True(outDocContents.Contains("<span>Hello again!</span>"));
    Assert.True(outDocContents.Contains("<span>Привет, мир!</span>"));
}
```

### أنظر أيضا

* class [HtmlSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../htmlsaveoptions/)
* المجسم [Aspose.Words](../../../)


