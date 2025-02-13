---
title: PdfSaveOptions.ZoomFactor
second_title: Справочник по API Aspose.Words для .NET
description: PdfSaveOptions свойство. Получает или задает значение определяющее коэффициент масштабирования в процентах для документа.
type: docs
weight: 300
url: /ru/net/aspose.words.saving/pdfsaveoptions/zoomfactor/
---
## PdfSaveOptions.ZoomFactor property

Получает или задает значение, определяющее коэффициент масштабирования (в процентах) для документа.

```csharp
public int ZoomFactor { get; set; }
```

### Примечания

Это значение используется, только если[`ZoomBehavior`](../zoombehavior/) установлен наZoomFactor .

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

* class [PdfSaveOptions](../)
* пространство имен [Aspose.Words.Saving](../../pdfsaveoptions/)
* сборка [Aspose.Words](../../../)


