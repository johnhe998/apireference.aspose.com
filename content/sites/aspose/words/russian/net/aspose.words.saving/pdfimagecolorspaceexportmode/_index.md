---
title: Enum PdfImageColorSpaceExportMode
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Saving.PdfImageColorSpaceExportMode перечисление. Указывает как цветовое пространство будет выбрано для изображений в документе PDF.
type: docs
weight: 5200
url: /ru/net/aspose.words.saving/pdfimagecolorspaceexportmode/
---
## PdfImageColorSpaceExportMode enumeration

Указывает, как цветовое пространство будет выбрано для изображений в документе PDF.

```csharp
public enum PdfImageColorSpaceExportMode
```

### Ценности

| Имя | Ценность | Описание |
| --- | --- | --- |
| Auto | `0` | Aspose.Words автоматически выбирает наиболее подходящее цветовое пространство для каждого изображения. |
| SimpleCmyk | `1` | Aspose.Words преобразует изображения RGB в цветовое пространство CMYK, используя простую формулу. |

### Примеры

Показывает, как установить другое цветовое пространство для изображений в документе, когда мы экспортируем его в PDF.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Jpeg image:");
builder.InsertImage(ImageDir + "Logo.jpg");
builder.InsertParagraph();
builder.Writeln("Png image:");
builder.InsertImage(ImageDir + "Transparent background logo.png");

// Создаем объект "PdfSaveOptions", который мы можем передать в метод "Сохранить" документа
// для изменения того, как этот метод преобразует документ в .PDF.
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();

// Установите для свойства "ImageColorSpaceExportMode" значение "PdfImageColorSpaceExportMode.Auto", чтобы получить Aspose.Words для
// автоматически выбирать цветовое пространство для изображений в документе, который он конвертирует в PDF.
// В большинстве случаев цветовое пространство будет RGB.
// Установите для свойства "ImageColorSpaceExportMode" значение "PdfImageColorSpaceExportMode.SimpleCmyk"
// чтобы использовать цветовое пространство CMYK для всех изображений в сохраненном PDF-файле.
// Aspose.Words также будет применять сжатие Flate ко всем изображениям и игнорировать значение свойства «ImageCompression».
pdfSaveOptions.ImageColorSpaceExportMode = pdfImageColorSpaceExportMode;

doc.Save(ArtifactsDir + "PdfSaveOptions.ImageColorSpaceExportMode.pdf", pdfSaveOptions);
```

### Смотрите также

* пространство имен [Aspose.Words.Saving](../../aspose.words.saving/)
* сборка [Aspose.Words](../../)


