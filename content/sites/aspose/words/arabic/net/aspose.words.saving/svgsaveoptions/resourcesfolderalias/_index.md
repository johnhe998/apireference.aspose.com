---
title: SvgSaveOptions.ResourcesFolderAlias
second_title: Aspose.Words لمراجع .NET API
description: SvgSaveOptions ملكية. يحدد اسم المجلد المستخدم لتكوين URIs للصور المكتوبة في مستند SVG . الافتراضي هولا شيء .
type: docs
weight: 60
url: /ar/net/aspose.words.saving/svgsaveoptions/resourcesfolderalias/
---
## SvgSaveOptions.ResourcesFolderAlias property

يحدد اسم المجلد المستخدم لتكوين URIs للصور المكتوبة في مستند SVG . الافتراضي هو`لا شيء` .

```csharp
public string ResourcesFolderAlias { get; set; }
```

### ملاحظات

عندما تقوم بحفظ ملف[`Document`](../../../aspose.words/document/)بتنسيق SVG ، يحتاج Aspose.Words إلى حفظ جميع الصور المضمنة في المستند كملفات قائمة بذاتها.[`ResourcesFolder`](../resourcesfolder/) يسمح لك بتحديد مكان حفظ الصور و`ResourcesFolderAlias` يسمح بتحديد كيفية إنشاء عناوين URI للصورة.

### أمثلة

يوضح كيفية معالجة وطباعة URIs للموارد المرتبطة التي تم إنشاؤها أثناء تحويل مستند إلى .svg.

```csharp
public void SvgResourceFolder()
{
    Document doc = new Document(MyDir + "Rendering.docx");

    SvgSaveOptions options = new SvgSaveOptions
    {
        SaveFormat = SaveFormat.Svg,
        ExportEmbeddedImages = false,
        ResourcesFolder = ArtifactsDir + "SvgResourceFolder",
        ResourcesFolderAlias = ArtifactsDir + "SvgResourceFolderAlias",
        ShowPageBorder = false,

        ResourceSavingCallback = new ResourceUriPrinter()
    };

    Directory.CreateDirectory(options.ResourcesFolderAlias);

    doc.Save(ArtifactsDir + "SvgSaveOptions.SvgResourceFolder.svg", options);
}

/// <summary>
/// يحسب ويطبع URIs للموارد المتضمنة بواسطة عندما يتم تحويلها إلى .svg.
/// </summary>
private class ResourceUriPrinter : IResourceSavingCallback
{
    void IResourceSavingCallback.ResourceSaving(ResourceSavingArgs args)
    {
        Console.WriteLine($"Resource #{++mSavedResourceCount} \"{args.ResourceFileName}\"");
        Console.WriteLine("\t" + args.ResourceFileUri);
    }

    private int mSavedResourceCount;
}
```

### أنظر أيضا

* class [SvgSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../svgsaveoptions/)
* المجسم [Aspose.Words](../../../)


