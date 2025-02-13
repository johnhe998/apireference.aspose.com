---
title: DocumentBuilder.MoveToSection
second_title: Справочник по API Aspose.Words для .NET
description: DocumentBuilder метод. Перемещает курсор в начало тела в указанном разделе.
type: docs
weight: 550
url: /ru/net/aspose.words/documentbuilder/movetosection/
---
## DocumentBuilder.MoveToSection method

Перемещает курсор в начало тела в указанном разделе.

```csharp
public void MoveToSection(int sectionIndex)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| sectionIndex | Int32 | Индекс раздела, к которому нужно перейти. |

### Примечания

Когда sectionIndex больше или равен 0, он указывает индекс from начала документа, где 0 является первым разделом. Когда sectionIndex меньше 0, , он указывает индекс с конца документа, где -1 является последним разделом.

Курсор переместится на первый абзац в **Тело** указанного раздела.

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

### Смотрите также

* class [DocumentBuilder](../)
* пространство имен [Aspose.Words](../../documentbuilder/)
* сборка [Aspose.Words](../../../)


