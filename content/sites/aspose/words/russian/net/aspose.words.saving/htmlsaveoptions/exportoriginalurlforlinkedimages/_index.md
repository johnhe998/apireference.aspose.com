---
title: HtmlSaveOptions.ExportOriginalUrlForLinkedImages
second_title: Справочник по API Aspose.Words для .NET
description: HtmlSaveOptions свойство. Указывает следует ли использовать исходный URLадрес в качестве URLадреса связанных изображений. Значение по умолчаниюЛОЖЬ .
type: docs
weight: 210
url: /ru/net/aspose.words.saving/htmlsaveoptions/exportoriginalurlforlinkedimages/
---
## HtmlSaveOptions.ExportOriginalUrlForLinkedImages property

Указывает, следует ли использовать исходный URL-адрес в качестве URL-адреса связанных изображений. Значение по умолчанию:`ЛОЖЬ` .

```csharp
public bool ExportOriginalUrlForLinkedImages { get; set; }
```

### Примечания

Если установлено значение`истинный`[`SourceFullName`](../../../aspose.words.drawing/imagedata/sourcefullname/) значение используется , поскольку URL связанных изображений и связанных изображений не загружаются в папку документа или[`ImagesFolder`](../imagesfolder/).

Если установлено значение`ЛОЖЬ` связанные изображения загружаются в папку документа или[`ImagesFolder`](../imagesfolder/) и URL каждого связанного изображения создается в зависимости от папки документа,[`ImagesFolder`](../imagesfolder/) и[`ImagesFolderAlias`](../imagesfolderalias/) характеристики.

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


