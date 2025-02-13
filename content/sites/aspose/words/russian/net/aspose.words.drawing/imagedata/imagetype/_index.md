---
title: ImageData.ImageType
second_title: Справочник по API Aspose.Words для .NET
description: ImageData свойство. Получает тип изображения.
type: docs
weight: 140
url: /ru/net/aspose.words.drawing/imagedata/imagetype/
---
## ImageData.ImageType property

Получает тип изображения.

```csharp
public ImageType ImageType { get; }
```

### Примеры

Показывает, как извлекать изображения из документа и сохранять их в локальной файловой системе в виде отдельных файлов.

```csharp
Document doc = new Document(MyDir + "Images.docx");

// Получить набор фигур из документа,
// и сохранить данные изображения каждой фигуры с изображением в виде файла в локальной файловой системе.
NodeCollection shapes = doc.GetChildNodes(NodeType.Shape, true);

Assert.AreEqual(9, shapes.Count(s => ((Shape)s).HasImage));

int imageIndex = 0;
foreach (Shape shape in shapes.OfType<Shape>())
{
    if (shape.HasImage)
    {
        // Данные изображения фигур могут содержать изображения многих возможных форматов изображений. 
        // Мы можем определить расширение файла для каждого изображения автоматически, исходя из его формата.
        string imageFileName =
            $"File.ExtractImages.{imageIndex}{FileFormatUtil.ImageTypeToExtension(shape.ImageData.ImageType)}";
        shape.ImageData.Save(ArtifactsDir + imageFileName);
        imageIndex++;
    }
}
```

### Смотрите также

* enum [ImageType](../../imagetype/)
* class [ImageData](../)
* пространство имен [Aspose.Words.Drawing](../../imagedata/)
* сборка [Aspose.Words](../../../)


