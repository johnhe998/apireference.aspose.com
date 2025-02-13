---
title: HtmlSaveOptions.ResourceFolder
second_title: Aspose.Words لمراجع .NET API
description: HtmlSaveOptions ملكية. يحدد مجلدًا ماديًا حيث يتم حفظ جميع الموارد مثل الصور والخطوط و CSS الخارجية عند تصدير document إلى HTML. الافتراضي هو عبارة عن سلسلة فارغة.
type: docs
weight: 420
url: /ar/net/aspose.words.saving/htmlsaveoptions/resourcefolder/
---
## HtmlSaveOptions.ResourceFolder property

يحدد مجلدًا ماديًا حيث يتم حفظ جميع الموارد مثل الصور والخطوط و CSS الخارجية عند تصدير document إلى HTML. الافتراضي هو عبارة عن سلسلة فارغة.

```csharp
public string ResourceFolder { get; set; }
```

### ملاحظات

`ResourceFolder` هي أبسط طريقة لتحديد مجلد حيث يجب كتابة جميع الموارد . هناك طريقة أخرى وهي استخدام الخصائص الفردية[`FontsFolder`](../fontsfolder/) و[`ImagesFolder`](../imagesfolder/) و و[`CssStyleSheetFileName`](../cssstylesheetfilename/).

`ResourceFolder` له أولوية أقل من المجلدات المحددة عبر[`FontsFolder`](../fontsfolder/) ، [`ImagesFolder`](../imagesfolder/) ، و[`CssStyleSheetFileName`](../cssstylesheetfilename/) . على سبيل المثال ، إذا كان both `ResourceFolder` و[`FontsFolder`](../fontsfolder/)تم تحديد الخطوط ، سيتم حفظها_ إلى[`FontsFolder`](../fontsfolder/) ، بينما سيتم حفظ الصور و CSS في`ResourceFolder`.

إذا كان المجلد المحدد بواسطة`ResourceFolder` غير موجود ، سيتم إنشاؤه تلقائيًا .

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


