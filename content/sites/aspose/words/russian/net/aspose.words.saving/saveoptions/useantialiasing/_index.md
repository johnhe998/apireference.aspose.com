---
title: SaveOptions.UseAntiAliasing
second_title: Справочник по API Aspose.Words для .NET
description: SaveOptions свойство. Получает или задает значение определяющее следует ли использовать сглаживание для рендеринга.
type: docs
weight: 210
url: /ru/net/aspose.words.saving/saveoptions/useantialiasing/
---
## SaveOptions.UseAntiAliasing property

Получает или задает значение, определяющее, следует ли использовать сглаживание для рендеринга.

```csharp
public bool UseAntiAliasing { get; set; }
```

### Примечания

Значение по умолчанию:`ЛОЖЬ` . Когда это значение установлено на`истинный` сглаживание используется для рендеринга.

Это свойство используется при экспорте документа в следующие форматы: Tiff ,Png ,Bmp , Jpeg ,Emf . Когда документ экспортируется в Html ,Mhtml а такжеEpub форматы эта опция используется для растровых изображений.

### Примеры

Показывает, как улучшить качество визуализированного документа с помощью SaveOptions.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Size = 60;
builder.Writeln("Some text.");

SaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);

doc.Save(ArtifactsDir + "Document.ImageSaveOptions.Default.jpg", options);

options.UseAntiAliasing = true;
options.UseHighQualityRendering = true;

doc.Save(ArtifactsDir + "Document.ImageSaveOptions.HighQuality.jpg", options);
```

### Смотрите также

* class [SaveOptions](../)
* пространство имен [Aspose.Words.Saving](../../saveoptions/)
* сборка [Aspose.Words](../../../)


