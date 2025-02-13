---
title: FixedPageSaveOptions.ColorMode
second_title: Справочник по API Aspose.Words для .NET
description: FixedPageSaveOptions свойство. Получает или задает значение определяющее способ отображения цветов.
type: docs
weight: 10
url: /ru/net/aspose.words.saving/fixedpagesaveoptions/colormode/
---
## FixedPageSaveOptions.ColorMode property

Получает или задает значение, определяющее способ отображения цветов.

```csharp
public ColorMode ColorMode { get; set; }
```

### Примечания

Значение по умолчаниюNormal .

### Примеры

Показывает, как изменить цвет изображения с помощью свойства сохранения параметров.

```csharp
Document doc = new Document(MyDir + "Images.docx");

// Создаем объект "PdfSaveOptions", который мы можем передать в метод "Сохранить" документа
// для изменения того, как этот метод преобразует документ в .PDF.
// Установите для свойства «ColorMode» значение «Оттенки серого», чтобы отображать все изображения из документа в черно-белом цвете.
// Размер выходного документа может быть больше с этой настройкой.
// Установите для свойства "ColorMode" значение "Нормальный", чтобы все изображения отображались в цвете.
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions { ColorMode = colorMode };

doc.Save(ArtifactsDir + "PdfSaveOptions.ColorRendering.pdf", pdfSaveOptions);
```

### Смотрите также

* enum [ColorMode](../../colormode/)
* class [FixedPageSaveOptions](../)
* пространство имен [Aspose.Words.Saving](../../fixedpagesaveoptions/)
* сборка [Aspose.Words](../../../)


