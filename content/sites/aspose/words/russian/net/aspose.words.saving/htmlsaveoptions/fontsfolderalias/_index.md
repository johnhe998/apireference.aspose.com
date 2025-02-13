---
title: HtmlSaveOptions.FontsFolderAlias
second_title: Справочник по API Aspose.Words для .NET
description: HtmlSaveOptions свойство. Указывает имя папки используемой для построения URI шрифтов записываемых в документ HTML. По умолчанию  пустая строка.
type: docs
weight: 330
url: /ru/net/aspose.words.saving/htmlsaveoptions/fontsfolderalias/
---
## HtmlSaveOptions.FontsFolderAlias property

Указывает имя папки, используемой для построения URI шрифтов, записываемых в документ HTML. По умолчанию — пустая строка.

```csharp
public string FontsFolderAlias { get; set; }
```

### Примечания

Когда вы сохраняете[`Document`](../../../aspose.words/document/) в формате HTML и[`ExportFontResources`](../exportfontresources/) установлен на`истинный` , Aspose.Words необходимо сохранять шрифты, используемые в документе, как отдельные файлы. [`FontsFolder`](../fontsfolder/) позволяет указать, где будут сохраняться шрифты и `FontsFolderAlias` позволяет указать, как будут создаваться URI шрифта.

Если`FontsFolderAlias` не является пустой строкой, то URI шрифта, написанный в HTML, будетFontsFolderAlias + &lt;имя файла шрифта&gt;.

Если`FontsFolderAlias` является пустой строкой, тогда URI шрифта, записанный в HTML, будетFontsFolder + &lt;имя файла шрифта&gt;.

Если`FontsFolderAlias`установлен в '.' (точка), то имя файла шрифта будет записано в HTML без пути независимо от других параметров.

Альтернативный способ указать имя папки для построения шрифта URIs — использовать[`ResourceFolderAlias`](../resourcefolderalias/).

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


