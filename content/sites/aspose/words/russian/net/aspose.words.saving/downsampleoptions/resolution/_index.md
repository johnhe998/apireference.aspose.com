---
title: DownsampleOptions.Resolution
second_title: Справочник по API Aspose.Words для .NET
description: DownsampleOptions свойство. Определяет разрешение в пикселях на дюйм до которого изображения должны быть уменьшены.
type: docs
weight: 30
url: /ru/net/aspose.words.saving/downsampleoptions/resolution/
---
## DownsampleOptions.Resolution property

Определяет разрешение в пикселях на дюйм, до которого изображения должны быть уменьшены.

```csharp
public int Resolution { get; set; }
```

### Примечания

Значение по умолчанию — 220 ppi.

### Примеры

Показывает, как изменить разрешение изображений в документе PDF.

```csharp
Document doc = new Document(MyDir + "Images.docx");

// Создаем объект "PdfSaveOptions", который мы можем передать в метод "Сохранить" документа
// для изменения того, как этот метод преобразует документ в .PDF.
PdfSaveOptions options = new PdfSaveOptions();

// По умолчанию Aspose.Words понижает разрешение всех изображений в документе, который мы сохраняем в PDF, до 220 пикселей на дюйм.
Assert.True(options.DownsampleOptions.DownsampleImages);
Assert.AreEqual(220, options.DownsampleOptions.Resolution);
Assert.AreEqual(0, options.DownsampleOptions.ResolutionThreshold);

doc.Save(ArtifactsDir + "PdfSaveOptions.DownsampleOptions.Default.pdf", options);

// Установите для свойства «Разрешение» значение «36», чтобы уменьшить разрешение всех изображений до 36 пикселей на дюйм.
options.DownsampleOptions.Resolution = 36;

// Установите свойство "ResolutionThreshold", чтобы применять понижающую дискретизацию только к
// изображения с разрешением выше 128 ppi.
options.DownsampleOptions.ResolutionThreshold = 128;

// Только первые два изображения из документа будут уменьшены на этом этапе.
doc.Save(ArtifactsDir + "PdfSaveOptions.DownsampleOptions.LowerResolution.pdf", options);
```

### Смотрите также

* class [DownsampleOptions](../)
* пространство имен [Aspose.Words.Saving](../../downsampleoptions/)
* сборка [Aspose.Words](../../../)


