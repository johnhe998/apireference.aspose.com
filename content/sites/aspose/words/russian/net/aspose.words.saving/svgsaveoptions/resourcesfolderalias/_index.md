---
title: SvgSaveOptions.ResourcesFolderAlias
second_title: Справочник по API Aspose.Words для .NET
description: SvgSaveOptions свойство. Указывает имя папки используемой для создания URI изображений записанных в документ SVG. По умолчаниюнулевой .
type: docs
weight: 60
url: /ru/net/aspose.words.saving/svgsaveoptions/resourcesfolderalias/
---
## SvgSaveOptions.ResourcesFolderAlias property

Указывает имя папки, используемой для создания URI изображений, записанных в документ SVG. По умолчанию:`нулевой` .

```csharp
public string ResourcesFolderAlias { get; set; }
```

### Примечания

Когда вы сохраняете[`Document`](../../../aspose.words/document/)в формате SVG Aspose.Words необходимо сохранить все изображения , встроенные в документ, как отдельные файлы.[`ResourcesFolder`](../resourcesfolder/) позволяет указать, где изображения будут сохранены и`ResourcesFolderAlias` позволяет указать, как будут создаваться URI изображения.

### Примеры

Показывает, как управлять и печатать URI связанных ресурсов, созданных при преобразовании документа в .svg.

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
/// Подсчитывает и печатает URI ресурсов, содержащихся в, когда они преобразуются в .svg.
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

### Смотрите также

* class [SvgSaveOptions](../)
* пространство имен [Aspose.Words.Saving](../../svgsaveoptions/)
* сборка [Aspose.Words](../../../)


