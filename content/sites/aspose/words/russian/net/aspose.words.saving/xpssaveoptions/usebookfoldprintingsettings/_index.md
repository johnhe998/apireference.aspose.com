---
title: XpsSaveOptions.UseBookFoldPrintingSettings
second_title: Справочник по API Aspose.Words для .NET
description: XpsSaveOptions свойство. Получает или задает логическое значение указывающее следует ли сохранять документ с использованием макета печати брошюры  если он указан черезMultiplePages .
type: docs
weight: 40
url: /ru/net/aspose.words.saving/xpssaveoptions/usebookfoldprintingsettings/
---
## XpsSaveOptions.UseBookFoldPrintingSettings property

Получает или задает логическое значение, указывающее, следует ли сохранять документ с использованием макета печати брошюры, , если он указан через[`MultiplePages`](../../../aspose.words/pagesetup/multiplepages/) .

```csharp
public bool UseBookFoldPrintingSettings { get; set; }
```

### Примечания

Если указан этот параметр,[`PageSet`](../../fixedpagesaveoptions/pageset/) игнорируется при сохранении. Это поведение соответствует MS Word. Если в параметрах страницы не указаны параметры печати сгибом книги, этот параметр не будет действовать.

### Примеры

Показывает, как сохранить документ в формате XPS в виде книжной складки.

```csharp
Document doc = new Document(MyDir + "Paragraphs.docx");

// Создаем объект "XpsSaveOptions", который мы можем передать в метод "Сохранить" документа
// для изменения того, как этот метод преобразует документ в .XPS.
XpsSaveOptions xpsOptions = new XpsSaveOptions(SaveFormat.Xps);

// Установите для свойства «UseBookFoldPrintingSettings» значение «true», чтобы упорядочить содержимое
// в выходной XPS таким образом, чтобы мы могли использовать его для создания буклета.
// Установите для свойства «UseBookFoldPrintingSettings» значение «false», чтобы XPS отображался нормально.
xpsOptions.UseBookFoldPrintingSettings = renderTextAsBookFold;

// Если мы визуализируем документ как буклет, мы должны установить «Несколько страниц»
// свойства объектов настройки страницы всех разделов на "MultiplePagesType.BookFoldPrinting".
if (renderTextAsBookFold)
    foreach (Section s in doc.Sections)
    {
        s.PageSetup.MultiplePages = MultiplePagesType.BookFoldPrinting;
    }

// Как только мы напечатаем этот документ, мы можем превратить его в буклет, сложив страницы
// выйти из принтера и сложить посередине.
doc.Save(ArtifactsDir + "XpsSaveOptions.BookFold.xps", xpsOptions);
```

### Смотрите также

* class [XpsSaveOptions](../)
* пространство имен [Aspose.Words.Saving](../../xpssaveoptions/)
* сборка [Aspose.Words](../../../)


