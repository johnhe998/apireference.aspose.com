---
title: PclSaveOptions.SaveFormat
second_title: Справочник по API Aspose.Words для .NET
description: PclSaveOptions свойство. Определяет формат в котором документ будет сохранен если используется этот объект параметров сохранения.Pcl .
type: docs
weight: 40
url: /ru/net/aspose.words.saving/pclsaveoptions/saveformat/
---
## PclSaveOptions.SaveFormat property

Определяет формат, в котором документ будет сохранен, если используется этот объект параметров сохранения.Pcl .

```csharp
public override SaveFormat SaveFormat { get; set; }
```

### Примеры

Показывает, как растрировать сложные элементы при сохранении документа в PCL.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

PclSaveOptions saveOptions = new PclSaveOptions
{
    SaveFormat = SaveFormat.Pcl,
    RasterizeTransformedElements = true
};

doc.Save(ArtifactsDir + "PclSaveOptions.RasterizeElements.pcl", saveOptions);
```

### Смотрите также

* enum [SaveFormat](../../../aspose.words/saveformat/)
* class [PclSaveOptions](../)
* пространство имен [Aspose.Words.Saving](../../pclsaveoptions/)
* сборка [Aspose.Words](../../../)


