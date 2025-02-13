---
title: PdfSaveOptions.ImageColorSpaceExportMode
second_title: Справочник по API Aspose.Words для .NET
description: PdfSaveOptions свойство. Указывает как цветовое пространство будет выбрано для изображений в документе PDF.
type: docs
weight: 160
url: /ru/net/aspose.words.saving/pdfsaveoptions/imagecolorspaceexportmode/
---
## PdfSaveOptions.ImageColorSpaceExportMode property

Указывает, как цветовое пространство будет выбрано для изображений в документе PDF.

```csharp
public PdfImageColorSpaceExportMode ImageColorSpaceExportMode { get; set; }
```

### Примечания

Значение по умолчанию:Auto .

ЕслиSimpleCmyk указано значение, [`ImageCompression`](../imagecompression/) опция игнорируется и Flate-сжатие используется для всех изображений в документе.

SimpleCmyk значение не поддерживается при сохранении в PDF/A. Auto вместо этого будет использоваться значение.

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

* enum [PdfImageColorSpaceExportMode](../../pdfimagecolorspaceexportmode/)
* class [PdfSaveOptions](../)
* пространство имен [Aspose.Words.Saving](../../pdfsaveoptions/)
* сборка [Aspose.Words](../../../)


