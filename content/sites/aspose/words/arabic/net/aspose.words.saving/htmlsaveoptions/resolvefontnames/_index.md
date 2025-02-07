---
title: HtmlSaveOptions.ResolveFontNames
second_title: Aspose.Words لمراجع .NET API
description: HtmlSaveOptions ملكية. يحدد ما إذا كانت أسماء عائلة الخط المستخدمة في المستند سيتم حلها واستبدالها وفقًا لـ FontSettings عند كتابتها في تنسيقات تستند إلى HTML.
type: docs
weight: 410
url: /ar/net/aspose.words.saving/htmlsaveoptions/resolvefontnames/
---
## HtmlSaveOptions.ResolveFontNames property

يحدد ما إذا كانت أسماء عائلة الخط المستخدمة في المستند سيتم حلها واستبدالها وفقًا لـ [`FontSettings`](../../../aspose.words/document/fontsettings/) عند كتابتها في تنسيقات تستند إلى HTML.

```csharp
public bool ResolveFontNames { get; set; }
```

### ملاحظات

بشكل افتراضي ، يتم تعيين هذا الخيار على`خاطئة`وأسماء عائلة الخطوط مكتوبة إلى HTML كما هو محدد في المستندات المصدر. هذا هو،[`FontSettings`](../../../aspose.words/document/fontsettings/) يتم تجاهلها ولا يتم إجراء تحليل أو استبدال لأسماء عائلة الخطوط.

إذا تم تعيين هذا الخيار على`حقيقي` يستخدم Aspose.Words[`FontSettings`](../../../aspose.words/document/fontsettings/) لحل كل اسم عائلة خط محدد في مستند مصدر في اسم عائلة خطوط متوفرة ، يتم استبدال الخط على النحو المطلوب.

### أمثلة

يوضح كيفية حل جميع أسماء الخطوط قبل كتابتها إلى HTML.

```csharp
Document doc = new Document(MyDir + "Missing font.docx");

// يحتوي هذا المستند على نص يسمي خطًا ليس لدينا.
Assert.NotNull(doc.FontInfos["28 Days Later"]);

// إذا لم يكن لدينا طريقة للحصول على هذا الخط ، ونريد أن نكون قادرين على عرض كل النص
// في هذا المستند بإخراج HTML ، يمكننا استبداله بخط آخر.
FontSettings fontSettings = new FontSettings
{
    SubstitutionSettings =
    {
        DefaultFontSubstitution =
        {
            DefaultFontName = "Arial",
            Enabled = true
        }
    }
};

doc.FontSettings = fontSettings;

HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
    // افتراضيًا ، يتم تعيين هذا الخيار على "False" و Aspose.Words يكتب أسماء الخطوط كما هو محدد في المستند المصدر
    ResolveFontNames = resolveFontNames
};

doc.Save(ArtifactsDir + "HtmlSaveOptions.ResolveFontNames.html", saveOptions);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlSaveOptions.ResolveFontNames.html");

Assert.True(resolveFontNames
    ? Regex.Match(outDocContents, "<span style=\"font-family:Arial\">").Success
    : Regex.Match(outDocContents, "<span style=\"font-family:\'28 Days Later\'\">").Success);
```

### أنظر أيضا

* class [HtmlSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../htmlsaveoptions/)
* المجسم [Aspose.Words](../../../)


