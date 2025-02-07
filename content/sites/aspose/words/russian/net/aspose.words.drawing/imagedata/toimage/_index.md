---
title: ImageData.ToImage
second_title: Справочник по API Aspose.Words для .NET
description: ImageData метод. Получает изображение хранящееся в форме какImage объект.
type: docs
weight: 220
url: /ru/net/aspose.words.drawing/imagedata/toimage/
---
## ImageData.ToImage method

Получает изображение, хранящееся в форме, какImage объект.

```csharp
public Image ToImage()
```

### Примечания

новыйImage объект создается каждый раз, когда вызывается этот метод.

Вызывающий объект несет ответственность за удаление объекта изображения.

### Примеры

Показывает, как сохранить все изображения из документа в файловую систему.

```csharp
Document imgSourceDoc = new Document(MyDir + "Images.docx");

// Формы с установленным флагом "HasImage" сохраняют и отображают все изображения документа.
IEnumerable<Shape> shapesWithImages = 
    imgSourceDoc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Where(s => s.HasImage);

// Проходим по каждой фигуре и сохраняем ее изображение.
ImageFormatConverter formatConverter = new ImageFormatConverter();

using (IEnumerator<Shape> enumerator = shapesWithImages.GetEnumerator())
{
    int shapeIndex = 0;

    while (enumerator.MoveNext())
    {
        ImageData imageData = enumerator.Current.ImageData;
        ImageFormat format = imageData.ToImage().RawFormat;
        string fileExtension = formatConverter.ConvertToString(format);

        using (FileStream fileStream = File.Create(ArtifactsDir + $"Drawing.SaveAllImages.{++shapeIndex}.{fileExtension}"))
            imageData.Save(fileStream);
    }
}
```

### Смотрите также

* class [ImageData](../)
* пространство имен [Aspose.Words.Drawing](../../imagedata/)
* сборка [Aspose.Words](../../../)


