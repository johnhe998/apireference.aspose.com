---
title: PdfSaveOptions.PreserveFormFields
second_title: Справочник по API Aspose.Words для .NET
description: PdfSaveOptions свойство. Указывает сохранять ли поля формы Microsoft Word как поля формы в PDF или преобразовывать их в текст. Значение по умолчаниюЛОЖЬ .
type: docs
weight: 240
url: /ru/net/aspose.words.saving/pdfsaveoptions/preserveformfields/
---
## PdfSaveOptions.PreserveFormFields property

Указывает, сохранять ли поля формы Microsoft Word как поля формы в PDF или преобразовывать их в текст. Значение по умолчанию:`ЛОЖЬ` .

```csharp
public bool PreserveFormFields { get; set; }
```

### Примечания

Поля формы Microsoft Word включают ввод текста, раскрывающийся список и элементы управления флажками.

При установке на`ЛОЖЬ` , эти поля будут экспортированы как текст в PDF. При установке на`истинный`, эти поля будут экспортированы как поля формы PDF.

При экспорте полей формы в PDF в качестве полей формы может произойти некоторая потеря форматирования, поскольку поля формы PDF form не поддерживают все функции полей формы Microsoft Word.

Кроме того, размер вывода зависит от размера содержимого, поскольку редактируемые формы в Microsoft Word являются встроенными объектами.

Редактируемые формы запрещены соответствием PDF/A.`ЛОЖЬ` значение будет использоваться автоматически при сохранении в PDF/A.

Поля формы не поддерживаются при сохранении в PDF/UA.`ЛОЖЬ` значение будет использоваться автоматически.

### Примеры

Показывает, как сохранить документ в формате PDF с помощью метода Save и класса PdfSaveOptions.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Please select a fruit: ");

// Вставьте поле со списком, которое позволит пользователю выбрать вариант из набора строк.
builder.InsertComboBox("MyComboBox", new[] { "Apple", "Banana", "Cherry" }, 0);

// Создаем объект "PdfSaveOptions", который мы можем передать в метод "Сохранить" документа
// для изменения того, как этот метод преобразует документ в .PDF.
PdfSaveOptions pdfOptions = new PdfSaveOptions();

// Установите для свойства «PreserveFormFields» значение «true», чтобы сохранить поля формы как интерактивные объекты в выходном PDF-файле.
// Установите для свойства "PreserveFormFields" значение "false", чтобы заморозить все поля формы в документе на
// их текущие значения и отобразить их в виде обычного текста в выходном PDF-файле.
pdfOptions.PreserveFormFields = preserveFormFields;

doc.Save(ArtifactsDir + "PdfSaveOptions.PreserveFormFields.pdf", pdfOptions);
```

### Смотрите также

* class [PdfSaveOptions](../)
* пространство имен [Aspose.Words.Saving](../../pdfsaveoptions/)
* сборка [Aspose.Words](../../../)


