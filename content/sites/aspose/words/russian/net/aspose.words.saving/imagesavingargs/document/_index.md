---
title: ImageSavingArgs.Document
second_title: Справочник по API Aspose.Words для .NET
description: ImageSavingArgs свойство. Получает объект документа который в данный момент сохраняется.
type: docs
weight: 20
url: /ru/net/aspose.words.saving/imagesavingargs/document/
---
## ImageSavingArgs.Document property

Получает объект документа, который в данный момент сохраняется.

```csharp
public Document Document { get; }
```

### Примеры

Показывает, как использовать обратный вызов сохранения изображения в процессе преобразования HTML.

```csharp
{
    Document doc = new Document(MyDir + "Rendering.docx");

    // Когда мы сохраняем документ в HTML, мы можем передать объект SaveOptions для назначения обратного вызова
    // для настройки процесса сохранения изображения.
    HtmlSaveOptions options = new HtmlSaveOptions();
    options.ImageSavingCallback = new ImageShapePrinter();

    doc.Save(ArtifactsDir + "HtmlSaveOptions.ImageSavingCallback.html", options);
}

/// <summary>
/// Выводит свойства каждого изображения по мере того, как процесс сохранения сохраняет его в файл изображения в локальной файловой системе
/// при экспорте документа в HTML.
/// </summary>
private class ImageShapePrinter : IImageSavingCallback
{
    void IImageSavingCallback.ImageSaving(ImageSavingArgs args)
    {
        args.KeepImageStreamOpen = false;
        Assert.True(args.IsImageAvailable);

        Console.WriteLine($"{args.Document.OriginalFileName.Split('\\').Last()} Image #{++mImageCount}");

        LayoutCollector layoutCollector = new LayoutCollector(args.Document);

        Console.WriteLine($"\tOn page:\t{layoutCollector.GetStartPageIndex(args.CurrentShape)}");
        Console.WriteLine($"\tDimensions:\t{args.CurrentShape.Bounds}");
        Console.WriteLine($"\tAlignment:\t{args.CurrentShape.VerticalAlignment}");
        Console.WriteLine($"\tWrap type:\t{args.CurrentShape.WrapType}");
        Console.WriteLine($"Output filename:\t{args.ImageFileName}\n");
    }

    private int mImageCount;
}
```

### Смотрите также

* class [Document](../../../aspose.words/document/)
* class [ImageSavingArgs](../)
* пространство имен [Aspose.Words.Saving](../../imagesavingargs/)
* сборка [Aspose.Words](../../../)


