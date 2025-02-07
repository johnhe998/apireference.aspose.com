---
title: FileFormatUtil.ImageTypeToExtension
second_title: Справочник по API Aspose.Words для .NET
description: FileFormatUtil метод. Преобразует перечислимое значение типа изображения Aspose.Words в расширение файла. Возвращаемое расширение представляет собой строчную строку с точкой в начале.
type: docs
weight: 50
url: /ru/net/aspose.words/fileformatutil/imagetypetoextension/
---
## FileFormatUtil.ImageTypeToExtension method

Преобразует перечислимое значение типа изображения Aspose.Words в расширение файла. Возвращаемое расширение представляет собой строчную строку с точкой в начале.

```csharp
public static string ImageTypeToExtension(ImageType imageType)
```

### Исключения

| исключение | условие |
| --- | --- |
| ArgumentException | Выбрасывает, когда не может преобразовать. |

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

* enum [ImageType](../../../aspose.words.drawing/imagetype/)
* class [FileFormatUtil](../)
* пространство имен [Aspose.Words](../../fileformatutil/)
* сборка [Aspose.Words](../../../)


