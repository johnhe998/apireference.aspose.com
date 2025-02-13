---
title: HtmlSaveOptions.ImagesFolderAlias
second_title: Справочник по API Aspose.Words для .NET
description: HtmlSaveOptions свойство. Указывает имя папки используемой для построения URI изображений записываемых в документ HTML. По умолчанию  пустая строка.
type: docs
weight: 380
url: /ru/net/aspose.words.saving/htmlsaveoptions/imagesfolderalias/
---
## HtmlSaveOptions.ImagesFolderAlias property

Указывает имя папки, используемой для построения URI изображений, записываемых в документ HTML. По умолчанию — пустая строка.

```csharp
public string ImagesFolderAlias { get; set; }
```

### Примечания

Когда вы сохраняете[`Document`](../../../aspose.words/document/) в формате HTML Aspose.Words необходимо сохранить все изображения , встроенные в документ, как отдельные файлы.[`ImagesFolder`](../imagesfolder/) позволяет указать, где изображения будут сохранены и`ImagesFolderAlias` позволяет указать, как будут создаваться URI изображения.

Если`ImagesFolderAlias`не является пустой строкой, тогда URI изображения, написанный в HTML, будетImagesFolderAlias + &lt;имя файла изображения&gt;.

Если`ImagesFolderAlias` является пустой строкой, тогда URI изображения, записанный в HTML, будетПапка изображений + &lt;имя файла изображения&gt;.

Если`ImagesFolderAlias` установлен в '.' (точка), то имя файла изображения будет записано в HTML без указания пути независимо от других параметров.

Альтернативный способ указать имя папки для построения образа URIs — использовать[`ResourceFolderAlias`](../resourcefolderalias/).

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


