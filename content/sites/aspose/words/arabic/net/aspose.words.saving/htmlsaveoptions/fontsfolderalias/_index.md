---
title: HtmlSaveOptions.FontsFolderAlias
second_title: Aspose.Words لمراجع .NET API
description: HtmlSaveOptions ملكية. يحدد اسم المجلد المستخدم في إنشاء عناوين URI للخط مكتوبة في مستند HTML. الافتراضي هو عبارة عن سلسلة فارغة.
type: docs
weight: 330
url: /ar/net/aspose.words.saving/htmlsaveoptions/fontsfolderalias/
---
## HtmlSaveOptions.FontsFolderAlias property

يحدد اسم المجلد المستخدم في إنشاء عناوين URI للخط مكتوبة في مستند HTML. الافتراضي هو عبارة عن سلسلة فارغة.

```csharp
public string FontsFolderAlias { get; set; }
```

### ملاحظات

عندما تقوم بحفظ ملف[`Document`](../../../aspose.words/document/) بتنسيق HTML و[`ExportFontResources`](../exportfontresources/) تم ضبط على`حقيقي` يحتاج Aspose.Words إلى حفظ الخطوط المستخدمة في المستند كملفات مستقلة. [`FontsFolder`](../fontsfolder/) يسمح لك بتحديد مكان حفظ الخطوط و `FontsFolderAlias` يسمح بتحديد كيفية إنشاء عناوين URI للخط.

إذا`FontsFolderAlias` ليست سلسلة فارغة ، ثم الخط URI المكتوب_ إلى HTML سيكونFontsFolderAlias + &lt;اسم ملف الخط&gt;.

إذا`FontsFolderAlias` عبارة عن سلسلة فارغة ، فسيكون الخط مكتوبًا إلى HTMLFontsFolder + &lt;اسم ملف الخط&gt;.

إذا`FontsFolderAlias`تم تعيينه على "." (نقطة) ، فسيتم كتابة اسم ملف الخط على HTML بدون مسار بغض النظر عن الخيارات الأخرى.

الطريقة البديلة لتحديد اسم المجلد لبناء الخط URIs هي استخدام[`ResourceFolderAlias`](../resourcefolderalias/).

### أمثلة

يوضح كيفية تعيين المجلدات والأسماء المستعارة للمجلدات للموارد المحفوظة خارجيًا والتي ستنشئها Aspose.Words عند حفظ مستند إلى HTML.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

HtmlSaveOptions options = new HtmlSaveOptions
{
    CssStyleSheetType = CssStyleSheetType.External,
    ExportFontResources = true,
    ImageResolution = 72,
    FontResourcesSubsettingSizeThreshold = 0,
    FontsFolder = ArtifactsDir + "Fonts",
    ImagesFolder = ArtifactsDir + "Images",
    ResourceFolder = ArtifactsDir + "Resources",
    FontsFolderAlias = "http://example.com/fonts "،
    ImagesFolderAlias = "http://example.com/images "،
    ResourceFolderAlias = "http://example.com/resources "،
    ExportOriginalUrlForLinkedImages = true
};

doc.Save(ArtifactsDir + "HtmlSaveOptions.FolderAlias.html", options);
```

### أنظر أيضا

* class [HtmlSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../htmlsaveoptions/)
* المجسم [Aspose.Words](../../../)


