---
title: ViewOptions.DoNotDisplayPageBoundaries
second_title: Справочник по API Aspose.Words для .NET
description: ViewOptions свойство. Отключает отображение пространства между верхней частью текста и верхним краем страницы.
type: docs
weight: 20
url: /ru/net/aspose.words.settings/viewoptions/donotdisplaypageboundaries/
---
## ViewOptions.DoNotDisplayPageBoundaries property

Отключает отображение пространства между верхней частью текста и верхним краем страницы.

```csharp
public bool DoNotDisplayPageBoundaries { get; set; }
```

### Примеры

Показывает, как скрыть вертикальные пробелы и верхние/нижние колонтитулы в параметрах просмотра.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Вставьте содержимое, занимающее 3 страницы.
builder.Writeln("Paragraph 1, Page 1.");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Paragraph 2, Page 2.");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Paragraph 3, Page 3.");

// Вставляем верхний и нижний колонтитулы.
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Writeln("This is the header.");
builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
builder.Writeln("This is the footer.");

// Этот документ содержит небольшое количество контента, занимающего несколько полных страниц.
// Установите для флага «DoNotDisplayPageBoundaries» значение «true», чтобы старые версии Microsoft Word пропускали заголовки,
// нижние колонтитулы и большую часть пробелов по вертикали при отображении нашего документа.
// Установите для флага «DoNotDisplayPageBoundaries» значение «false», чтобы получить более старые версии Microsoft Word
// для нормального отображения нашего документа.
doc.ViewOptions.DoNotDisplayPageBoundaries = doNotDisplayPageBoundaries;

doc.Save(ArtifactsDir + "ViewOptions.DisplayPageBoundaries.doc");
```

### Смотрите также

* class [ViewOptions](../)
* пространство имен [Aspose.Words.Settings](../../viewoptions/)
* сборка [Aspose.Words](../../../)


