---
title: RtfSaveOptions.SaveImagesAsWmf
second_title: Справочник по API Aspose.Words для .NET
description: RtfSaveOptions свойство. При значении true все изображения будут сохранены в формате WMF.
type: docs
weight: 50
url: /ru/net/aspose.words.saving/rtfsaveoptions/saveimagesaswmf/
---
## RtfSaveOptions.SaveImagesAsWmf property

При значении true все изображения будут сохранены в формате WMF.

```csharp
public bool SaveImagesAsWmf { get; set; }
```

### Примечания

Этот параметр может помочь избежать появления предупреждающих сообщений WordPad.

### Примеры

Показывает, как преобразовать все изображения в документе в формат метафайла Windows при сохранении документа в формате RTF.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Jpeg image:");
Shape imageShape = builder.InsertImage(ImageDir + "Logo.jpg");

Assert.AreEqual(ImageType.Jpeg, imageShape.ImageData.ImageType);

builder.InsertParagraph();
builder.Writeln("Png image:");
imageShape = builder.InsertImage(ImageDir + "Transparent background logo.png");

Assert.AreEqual(ImageType.Png, imageShape.ImageData.ImageType);

// Создайте объект «RtfSaveOptions», чтобы передать его методу «Сохранить» документа, чтобы изменить способ его сохранения в формате RTF.
RtfSaveOptions rtfSaveOptions = new RtfSaveOptions();

// Установите для свойства «SaveImagesAsWmf» значение «true», чтобы преобразовать все изображения в документе в WMF при сохранении в RTF.
// Это поможет читателям, таким как WordPad, прочитать наш документ.
// Установите для свойства "SaveImagesAsWmf" значение "false", чтобы сохранить исходный формат всех изображений в документе
// когда мы сохраняем его в RTF. Это позволит сохранить качество изображений за счет совместимости со старыми ридерами RTF.
rtfSaveOptions.SaveImagesAsWmf = saveImagesAsWmf;

doc.Save(ArtifactsDir + "RtfSaveOptions.SaveImagesAsWmf.rtf", rtfSaveOptions);

doc = new Document(ArtifactsDir + "RtfSaveOptions.SaveImagesAsWmf.rtf");

NodeCollection shapes = doc.GetChildNodes(NodeType.Shape, true);

if (saveImagesAsWmf)
{
    Assert.AreEqual(ImageType.Wmf, ((Shape)shapes[0]).ImageData.ImageType);
    Assert.AreEqual(ImageType.Wmf, ((Shape)shapes[1]).ImageData.ImageType);
}
else
{
    Assert.AreEqual(ImageType.Jpeg, ((Shape)shapes[0]).ImageData.ImageType);
    Assert.AreEqual(ImageType.Png, ((Shape)shapes[1]).ImageData.ImageType);
}
```

### Смотрите также

* class [RtfSaveOptions](../)
* пространство имен [Aspose.Words.Saving](../../rtfsaveoptions/)
* сборка [Aspose.Words](../../../)


