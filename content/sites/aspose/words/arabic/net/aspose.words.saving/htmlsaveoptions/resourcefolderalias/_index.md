---
title: HtmlSaveOptions.ResourceFolderAlias
second_title: Aspose.Words لمراجع .NET API
description: HtmlSaveOptions ملكية. يحدد اسم المجلد المستخدم لإنشاء URIs لجميع الموارد المكتوبة في مستند HTML. الافتراضي هو سلسلة فارغة.
type: docs
weight: 430
url: /ar/net/aspose.words.saving/htmlsaveoptions/resourcefolderalias/
---
## HtmlSaveOptions.ResourceFolderAlias property

يحدد اسم المجلد المستخدم لإنشاء URIs لجميع الموارد المكتوبة في مستند HTML. الافتراضي هو سلسلة فارغة.

```csharp
public string ResourceFolderAlias { get; set; }
```

### ملاحظات

`ResourceFolderAlias` هي أبسط طريقة لتحديد كيفية إنشاء URIs لجميع ملفات الموارد. يمكن تحديد نفس المعلومات للصور والخطوط بشكل منفصل عبر[`ImagesFolderAlias`](../imagesfolderalias/) و[`FontsFolderAlias`](../fontsfolderalias/) الخصائص ، على التوالي. ومع ذلك ، لا توجد خاصية فردية لـ CSS.

`ResourceFolderAlias` له أولوية أقل من[`FontsFolderAlias`](../fontsfolderalias/) و[`ImagesFolderAlias`](../imagesfolderalias/) . على سبيل المثال ، إذا كان كلاهما`ResourceFolderAlias` و[`FontsFolderAlias`](../fontsfolderalias/) محددة ، سيتم إنشاء URIs للخطوط باستخدام [`FontsFolderAlias`](../fontsfolderalias/) ، بينما سيتم إنشاء URIs للصور و CSS باستخدام `ResourceFolderAlias`.

إذا`ResourceFolderAlias` فارغ ،[`ResourceFolder`](../resourcefolder/)سيتم استخدام قيمة الخاصية لإنشاء محددات الموارد المنتظمة (URIs).

إذا`ResourceFolderAlias` تم تعيينه على "." (نقطة) ، ستحتوي URIs على أسماء الملفات فقط ، بدون أي مسار.

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


