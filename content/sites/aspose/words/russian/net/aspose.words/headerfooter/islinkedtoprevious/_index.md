---
title: HeaderFooter.IsLinkedToPrevious
second_title: Справочник по API Aspose.Words для .NET
description: HeaderFooter свойство. Истинно если этот верхний или нижний колонтитул связан с соответствующим верхним или нижним колонтитулом в предыдущем разделе.
type: docs
weight: 40
url: /ru/net/aspose.words/headerfooter/islinkedtoprevious/
---
## HeaderFooter.IsLinkedToPrevious property

Истинно, если этот верхний или нижний колонтитул связан с соответствующим верхним или нижним колонтитулом в предыдущем разделе.

```csharp
public bool IsLinkedToPrevious { get; set; }
```

### Примечания

Значение по умолчанию верно.

Обратите внимание, когда ваша ссылка находится в верхнем или нижнем колонтитуле, ее содержимое очищается.

### Примеры

Показывает, как связать верхние и нижние колонтитулы между разделами.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Section 1");
builder.InsertBreak(BreakType.SectionBreakNewPage);
builder.Write("Section 2");
builder.InsertBreak(BreakType.SectionBreakNewPage);
builder.Write("Section 3");

// Переходим к первому разделу и создаем верхний и нижний колонтитулы. По умолчанию,
// верхний и нижний колонтитулы будут отображаться только на страницах в том разделе, который их содержит.
builder.MoveToSection(0);

builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("This is the header, which will be displayed in sections 1 and 2.");

builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
builder.Write("This is the footer, which will be displayed in sections 1, 2 and 3.");

// Мы можем связать верхние/нижние колонтитулы раздела с верхними/нижними колонтитулами предыдущего раздела
// чтобы позволить ссылочному разделу отображать верхние/нижние колонтитулы связанного раздела.
doc.Sections[1].HeadersFooters.LinkToPrevious(true);

// Каждый раздел по-прежнему будет иметь свои собственные объекты верхнего/нижнего колонтитула. Когда мы связываем разделы,
// раздел ссылок будет отображать верхний и нижний колонтитулы связанного раздела, сохраняя при этом свои собственные.
Assert.AreNotEqual(doc.Sections[0].HeadersFooters[0], doc.Sections[1].HeadersFooters[0]);
Assert.AreNotEqual(doc.Sections[0].HeadersFooters[0].ParentSection, doc.Sections[1].HeadersFooters[0].ParentSection);

// Свяжите верхние/нижние колонтитулы третьего раздела с верхними/нижними колонтитулами второго раздела.
// Второй раздел уже связан с верхним/нижним колонтитулом первого раздела,
// таким образом, ссылка на второй раздел создаст цепочку ссылок.
// Первый, второй и теперь третий разделы будут отображать заголовки первого раздела.
doc.Sections[2].HeadersFooters.LinkToPrevious(true);

// Мы можем отменить связь верхнего/нижнего колонтитула предыдущего раздела, передав «false» при вызове метода LinkToPrevious.
doc.Sections[2].HeadersFooters.LinkToPrevious(false);

// Мы также можем выбрать только определенный тип верхнего/нижнего колонтитула для ссылки, используя этот метод.
// Третий раздел теперь будет иметь тот же нижний колонтитул, что и второй и первый разделы, но не заголовок.
doc.Sections[2].HeadersFooters.LinkToPrevious(HeaderFooterType.FooterPrimary, true);

// Верхний/нижний колонтитулы первого раздела не могут ссылаться ни на что, потому что предыдущего раздела нет.
Assert.AreEqual(2, doc.Sections[0].HeadersFooters.Count);
Assert.AreEqual(2, doc.Sections[0].HeadersFooters.Count(hf => !((HeaderFooter)hf).IsLinkedToPrevious));

// Все верхние/нижние колонтитулы второго раздела связаны с верхними/нижними колонтитулами первого раздела.
Assert.AreEqual(6, doc.Sections[1].HeadersFooters.Count);
Assert.AreEqual(6, doc.Sections[1].HeadersFooters.Count(hf => ((HeaderFooter)hf).IsLinkedToPrevious));

// В третьем разделе только нижний колонтитул связан с нижним колонтитулом первого раздела через второй раздел.
Assert.AreEqual(6, doc.Sections[2].HeadersFooters.Count);
Assert.AreEqual(5, doc.Sections[2].HeadersFooters.Count(hf => !((HeaderFooter)hf).IsLinkedToPrevious));
Assert.True(doc.Sections[2].HeadersFooters[3].IsLinkedToPrevious);

doc.Save(ArtifactsDir + "HeaderFooter.Link.docx");
```

### Смотрите также

* class [HeaderFooter](../)
* пространство имен [Aspose.Words](../../headerfooter/)
* сборка [Aspose.Words](../../../)


