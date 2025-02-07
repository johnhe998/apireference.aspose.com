---
title: ImageSavingArgs.CurrentShape
second_title: Справочник по API Aspose.Words для .NET
description: ImageSavingArgs свойство. ПолучаетShapeBase объект соответствующий фигуре или групповой фигуре  которую нужно сохранить.
type: docs
weight: 10
url: /ru/net/aspose.words.saving/imagesavingargs/currentshape/
---
## ImageSavingArgs.CurrentShape property

Получает[`ShapeBase`](../../../aspose.words.drawing/shapebase/) объект, соответствующий фигуре или групповой фигуре , которую нужно сохранить.

```csharp
public ShapeBase CurrentShape { get; }
```

### Примечания

[`IImageSavingCallback`](../../iimagesavingcallback/) может быть запущен при сохранении формы или формы группы. Вот почему свойство[`ShapeBase`](../../../aspose.words.drawing/shapebase/) тип. Вы можете проверить, является ли это формой группы, сравнивая [`ShapeType`](../../../aspose.words.drawing/shapebase/shapetype/) сGroup или приведя его к одному из производных классов: [`Shape`](../../../aspose.words.drawing/shape/) или же[`GroupShape`](../../../aspose.words.drawing/groupshape/).

Aspose.Words использует имя файла документа и уникальный номер для создания уникального имени файла для каждого изображения, найденного в документе. Вы можете использовать`CurrentShape` свойство для создания «лучшего» имени файла путем изучения свойств формы, таких как[`Title`](../../../aspose.words.drawing/imagedata/title/) (только форма),[`SourceFullName`](../../../aspose.words.drawing/imagedata/sourcefullname/) (только форма) и[`Name`](../../../aspose.words.drawing/shapebase/name/)Конечно, вы можете создавать имена файлов, используя любые другие свойства или критерии , но обратите внимание, что имена дочерних файлов должны быть уникальными в рамках операции экспорта.

Некоторые изображения в документе могут быть недоступны. Чтобы проверить доступность образа , используйте[`IsImageAvailable`](../isimageavailable/) имущество.

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

* class [ShapeBase](../../../aspose.words.drawing/shapebase/)
* class [ImageSavingArgs](../)
* пространство имен [Aspose.Words.Saving](../../imagesavingargs/)
* сборка [Aspose.Words](../../../)


