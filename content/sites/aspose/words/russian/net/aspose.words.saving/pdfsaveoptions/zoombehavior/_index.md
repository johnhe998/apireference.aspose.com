---
title: PdfSaveOptions.ZoomBehavior
second_title: Справочник по API Aspose.Words для .NET
description: PdfSaveOptions свойство. Получает или задает значение определяющее какой тип масштабирования следует применять при открытии документа в средстве просмотра PDF.
type: docs
weight: 290
url: /ru/net/aspose.words.saving/pdfsaveoptions/zoombehavior/
---
## PdfSaveOptions.ZoomBehavior property

Получает или задает значение, определяющее, какой тип масштабирования следует применять при открытии документа в средстве просмотра PDF.

```csharp
public PdfZoomBehavior ZoomBehavior { get; set; }
```

### Примечания

Значение по умолчанию:None , то есть подгонка не применяется.

### Примеры

Показывает, как установить масштабирование по умолчанию, применяемое программой чтения при открытии обработанного PDF-документа.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

// Создаем объект "PdfSaveOptions", который мы можем передать в метод "Сохранить" документа
// для изменения того, как этот метод преобразует документ в .PDF.
// Установите свойство "ZoomBehavior" в "PdfZoomBehavior.ZoomFactor", чтобы программа для чтения PDF
// применяем коэффициент масштабирования в процентах, когда мы открываем документ с его помощью.
// Установите для свойства "ZoomFactor" значение "25", чтобы присвоить коэффициенту масштабирования значение 25%.
PdfSaveOptions options = new PdfSaveOptions
{
    ZoomBehavior = PdfZoomBehavior.ZoomFactor,
    ZoomFactor = 25
};

// Когда мы откроем этот документ с помощью программы для чтения, такой как Adobe Acrobat, мы увидим, что документ масштабируется до 1/4 его фактического размера.
doc.Save(ArtifactsDir + "PdfSaveOptions.ZoomBehaviour.pdf", options);
```

### Смотрите также

* enum [PdfZoomBehavior](../../pdfzoombehavior/)
* class [PdfSaveOptions](../)
* пространство имен [Aspose.Words.Saving](../../pdfsaveoptions/)
* сборка [Aspose.Words](../../../)


