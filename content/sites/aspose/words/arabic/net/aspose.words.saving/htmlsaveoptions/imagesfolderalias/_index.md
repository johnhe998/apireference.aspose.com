---
title: HtmlSaveOptions.ImagesFolderAlias
second_title: Aspose.Words لمراجع .NET API
description: HtmlSaveOptions ملكية. يحدد اسم المجلد المستخدم في إنشاء عناوين URI للصورة مكتوبة في مستند HTML. الافتراضي هو عبارة عن سلسلة فارغة.
type: docs
weight: 380
url: /ar/net/aspose.words.saving/htmlsaveoptions/imagesfolderalias/
---
## HtmlSaveOptions.ImagesFolderAlias property

يحدد اسم المجلد المستخدم في إنشاء عناوين URI للصورة مكتوبة في مستند HTML. الافتراضي هو عبارة عن سلسلة فارغة.

```csharp
public string ImagesFolderAlias { get; set; }
```

### ملاحظات

عندما تقوم بحفظ ملف[`Document`](../../../aspose.words/document/) بتنسيق HTML ، يحتاج Aspose.Words إلى حفظ جميع الصور المضمنة في المستند كملفات قائمة بذاتها.[`ImagesFolder`](../imagesfolder/) يسمح لك بتحديد مكان حفظ الصور و`ImagesFolderAlias` يسمح بتحديد كيفية إنشاء عناوين URI للصورة.

إذا`ImagesFolderAlias`ليست سلسلة فارغة ، فإن صورة URI المكتوبة إلى HTML ستكونImagesFolderAlias + &lt;اسم ملف الصورة&gt;.

إذا`ImagesFolderAlias` عبارة عن سلسلة فارغة ، فسيكون عنوان URI للصورة المكتوب إلى HTMLImagesFolder + &lt;اسم ملف الصورة&gt;.

إذا`ImagesFolderAlias` تم تعيينه على "." (نقطة) ، فسيتم كتابة اسم ملف الصورة إلى HTML بدون مسار بغض النظر عن الخيارات الأخرى.

الطريقة البديلة لتحديد اسم المجلد لبناء صورة URIs هي استخدام[`ResourceFolderAlias`](../resourcefolderalias/).

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


