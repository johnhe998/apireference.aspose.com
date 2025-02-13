---
title: PageSetup.CharactersPerLine
second_title: Справочник по API Aspose.Words для .NET
description: PageSetup свойство. Получает или задает количество символов в строке в сетке документа.
type: docs
weight: 100
url: /ru/net/aspose.words/pagesetup/charactersperline/
---
## PageSetup.CharactersPerLine property

Получает или задает количество символов в строке в сетке документа.

```csharp
public int CharactersPerLine { get; set; }
```

### Примечания

Минимальное значение свойства равно 1. Максимальное значение зависит от ширины страницы и размера шрифта стиля Normal . Минимальный шаг символов составляет 90 процентов от размера шрифта. Например, максимальное количество символов в строке страницы Letter с полями в один дюйм равно 43.

По умолчанию свойство имеет значение, при котором шаг символов равен размеру шрифта стиля Normal .

### Примеры

Показывает, как указать число символов, которое может содержаться в каждой строке.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Включите питчинг, а затем используйте его, чтобы установить количество символов в строке в этом разделе.
builder.PageSetup.LayoutMode = SectionLayoutMode.Grid;
builder.PageSetup.CharactersPerLine = 10;

// Количество символов также зависит от размера шрифта.
doc.Styles["Normal"].Font.Size = 20;

Assert.AreEqual(8, doc.FirstSection.PageSetup.CharactersPerLine);

builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");

doc.Save(ArtifactsDir + "PageSetup.CharactersPerLine.docx");
```

### Смотрите также

* class [PageSetup](../)
* пространство имен [Aspose.Words](../../pagesetup/)
* сборка [Aspose.Words](../../../)


