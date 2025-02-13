---
title: PdfSaveOptions.AdditionalTextPositioning
second_title: Справочник по API Aspose.Words для .NET
description: PdfSaveOptions свойство. Флаг указывающий следует ли писать дополнительные операторы позиционирования текста или нет.
type: docs
weight: 20
url: /ru/net/aspose.words.saving/pdfsaveoptions/additionaltextpositioning/
---
## PdfSaveOptions.AdditionalTextPositioning property

Флаг, указывающий, следует ли писать дополнительные операторы позиционирования текста или нет.

```csharp
public bool AdditionalTextPositioning { get; set; }
```

### Примечания

Если`истинный` , дополнительные операторы позиционирования текста записываются в выходной PDF-файл. Это может помочь решить проблемы с неточным позиционированием текста на некоторых принтерах. Недостатком является увеличенный размер документа PDF.

Значение по умолчанию`ЛОЖЬ`.

### Примеры

Покажите, как писать дополнительные операторы позиционирования текста.

```csharp
Document doc = new Document(MyDir + "Text positioning operators.docx");

// Создаем объект "PdfSaveOptions", который мы можем передать в метод "Сохранить" документа
// для изменения того, как этот метод преобразует документ в .PDF.
PdfSaveOptions saveOptions = new PdfSaveOptions
{
    TextCompression = PdfTextCompression.None,

    // Установите для свойства "AdditionalTextPositioning" значение "true", чтобы попытаться исправить неверный
    // позиционирование элемента в выходном PDF-файле, если таковое имеется, за счет увеличения размера файла.
    // Установите для свойства "AdditionalTextPositioning" значение "false", чтобы документ отображался как обычно.
    AdditionalTextPositioning = applyAdditionalTextPositioning
};

doc.Save(ArtifactsDir + "PdfSaveOptions.AdditionalTextPositioning.pdf", saveOptions);
```

### Смотрите также

* class [PdfSaveOptions](../)
* пространство имен [Aspose.Words.Saving](../../pdfsaveoptions/)
* сборка [Aspose.Words](../../../)


