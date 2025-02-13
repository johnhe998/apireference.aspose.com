---
title: HtmlSaveOptions.ResourceFolder
second_title: Справочник по API Aspose.Words для .NET
description: HtmlSaveOptions свойство. Указывает физическую папку в которой сохраняются все ресурсы такие как изображения шрифты и внешний CSS когда документ экспортируется в HTML. По умолчанию это пустая строка.
type: docs
weight: 420
url: /ru/net/aspose.words.saving/htmlsaveoptions/resourcefolder/
---
## HtmlSaveOptions.ResourceFolder property

Указывает физическую папку, в которой сохраняются все ресурсы, такие как изображения, шрифты и внешний CSS, когда документ экспортируется в HTML. По умолчанию это пустая строка.

```csharp
public string ResourceFolder { get; set; }
```

### Примечания

`ResourceFolder` — самый простой способ указать папку, в которую должны быть записаны все ресурсы. Другой способ — использовать отдельные свойства[`FontsFolder`](../fontsfolder/) ,[`ImagesFolder`](../imagesfolder/) , и[`CssStyleSheetFileName`](../cssstylesheetfilename/).

`ResourceFolder` имеет более низкий приоритет, чем папки, указанные через[`FontsFolder`](../fontsfolder/) , [`ImagesFolder`](../imagesfolder/) , а также[`CssStyleSheetFileName`](../cssstylesheetfilename/) . Например, если оба `ResourceFolder` а также[`FontsFolder`](../fontsfolder/)указаны, шрифты будут сохранены в[`FontsFolder`](../fontsfolder/) , а изображения и CSS будут сохранены в`ResourceFolder`.

Если папка, указанная`ResourceFolder` не существует, он будет создан автоматически.

### Примеры

Показывает, как установить папки и псевдонимы папок для внешне сохраненных ресурсов, которые Aspose.Words создаст при сохранении документа в HTML.

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
    FontsFolderAlias = "http://example.com/шрифты",
    ImagesFolderAlias = "http://example.com/images",
    ResourceFolderAlias = "http://example.com/resources",
    ExportOriginalUrlForLinkedImages = true
};

doc.Save(ArtifactsDir + "HtmlSaveOptions.FolderAlias.html", options);
```

### Смотрите также

* class [HtmlSaveOptions](../)
* пространство имен [Aspose.Words.Saving](../../htmlsaveoptions/)
* сборка [Aspose.Words](../../../)


