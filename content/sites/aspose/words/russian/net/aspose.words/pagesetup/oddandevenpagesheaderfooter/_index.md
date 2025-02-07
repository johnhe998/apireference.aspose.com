---
title: PageSetup.OddAndEvenPagesHeaderFooter
second_title: Справочник по API Aspose.Words для .NET
description: PageSetup свойство. Истинныйесли документ имеет разные верхние и нижние колонтитулы для четных и нечетных страниц.
type: docs
weight: 270
url: /ru/net/aspose.words/pagesetup/oddandevenpagesheaderfooter/
---
## PageSetup.OddAndEvenPagesHeaderFooter property

**Истинный**если документ имеет разные верхние и нижние колонтитулы для четных и нечетных страниц.

```csharp
public bool OddAndEvenPagesHeaderFooter { get; set; }
```

### Примечания

Обратите внимание: изменение этого свойства влияет на все разделы документа.

### Примеры

Показывает, как создавать верхние и нижние колонтитулы в документе с помощью DocumentBuilder.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Указываем, что нам нужны разные верхние и нижние колонтитулы для первой, четной и нечетной страниц.
builder.PageSetup.DifferentFirstPageHeaderFooter = true;
builder.PageSetup.OddAndEvenPagesHeaderFooter = true;

// Создайте заголовки, затем добавьте в документ три страницы для отображения каждого типа заголовков.
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.Write("Header for the first page");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
builder.Write("Header for even pages");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Header for all other pages");

builder.MoveToSection(0);
builder.Writeln("Page1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page2");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page3");

doc.Save(ArtifactsDir + "DocumentBuilder.HeadersAndFooters.docx");
```

Показывает, как включить или отключить верхние/нижние колонтитулы четных страниц.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Ниже приведены два типа верхних/нижних колонтитулов.
// 1 - «Основной» верхний/нижний колонтитул, который появляется на каждой странице раздела.
// Мы можем переопределить основной верхний/нижний колонтитул первой и четной верхней/нижней страницей.
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Writeln("Primary header.");

builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
builder.Writeln("Primary footer.");

// 2 - "Четный" верхний/нижний колонтитул, который появляется на каждой четной странице этого раздела.
builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
builder.Writeln("Even page header.");

builder.MoveToHeaderFooter(HeaderFooterType.FooterEven);
builder.Writeln("Even page footer.");

builder.MoveToSection(0);
builder.Writeln("Page 1.");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page 2.");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page 3.");

// Каждый раздел имеет объект "PageSetup", который определяет свойства, связанные с внешним видом страницы
// такие как ориентация, размер и границы.
// Установите для свойства "OddAndEvenPagesHeaderFooter" значение "true"
// для отображения верхнего/нижнего колонтитула четной страницы на четных страницах.
// Установите для свойства "OddAndEvenPagesHeaderFooter" значение "false"
// для отображения основного верхнего/нижнего колонтитула на четных страницах.
builder.PageSetup.OddAndEvenPagesHeaderFooter = oddAndEvenPagesHeaderFooter;

doc.Save(ArtifactsDir + "PageSetup.OddAndEvenPagesHeaderFooter.docx");
```

### Смотрите также

* class [PageSetup](../)
* пространство имен [Aspose.Words](../../pagesetup/)
* сборка [Aspose.Words](../../../)


