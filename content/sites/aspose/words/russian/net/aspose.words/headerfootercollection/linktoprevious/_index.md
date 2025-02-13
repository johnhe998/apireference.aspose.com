---
title: HeaderFooterCollection.LinkToPrevious
second_title: Справочник по API Aspose.Words для .NET
description: HeaderFooterCollection метод. Связывает или разъединяет все верхние и нижние колонтитулы с соответствующими верхними и нижними колонтитулами в предыдущем разделе.
type: docs
weight: 20
url: /ru/net/aspose.words/headerfootercollection/linktoprevious/
---
## LinkToPrevious(bool) {#linktoprevious_1}

Связывает или разъединяет все верхние и нижние колонтитулы с соответствующими верхними и нижними колонтитулами в предыдущем разделе.

```csharp
public void LinkToPrevious(bool isLinkToPrevious)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| isLinkToPrevious | Boolean | Значение true, чтобы связать верхние и нижние колонтитулы с предыдущим разделом; false, чтобы отменить их связь. |

### Примечания

Если какой-либо из верхних или нижних колонтитулов не существует, создает их автоматически.

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

* class [HeaderFooterCollection](../)
* пространство имен [Aspose.Words](../../headerfootercollection/)
* сборка [Aspose.Words](../../../)

---

## LinkToPrevious(HeaderFooterType, bool) {#linktoprevious}

Связывает или разъединяет указанный верхний или нижний колонтитул с соответствующим верхним или нижним колонтитулом в предыдущем разделе.

```csharp
public void LinkToPrevious(HeaderFooterType headerFooterType, bool isLinkToPrevious)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| headerFooterType | HeaderFooterType | А[`HeaderFooterType`](../../headerfootertype/) value , указывающий верхний или нижний колонтитул для связывания/отсоединения. |
| isLinkToPrevious | Boolean | Значение true, чтобы связать верхний или нижний колонтитул с предыдущим разделом; значение false, чтобы отменить связь. |

### Примечания

Если верхний или нижний колонтитул указанного типа не существует, он создается автоматически.

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

* enum [HeaderFooterType](../../headerfootertype/)
* class [HeaderFooterCollection](../)
* пространство имен [Aspose.Words](../../headerfootercollection/)
* сборка [Aspose.Words](../../../)


