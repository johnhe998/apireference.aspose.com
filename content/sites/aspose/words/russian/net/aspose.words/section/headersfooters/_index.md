---
title: Section.HeadersFooters
second_title: Справочник по API Aspose.Words для .NET
description: Section свойство. Предоставляет доступ к верхним и нижним колонтитулам раздела.
type: docs
weight: 30
url: /ru/net/aspose.words/section/headersfooters/
---
## Section.HeadersFooters property

Предоставляет доступ к верхним и нижним колонтитулам раздела.

```csharp
public HeaderFooterCollection HeadersFooters { get; }
```

### Примеры

Показывает, как заменить текст в нижнем колонтитуле документа.

```csharp
Document doc = new Document(MyDir + "Footer.docx");

HeaderFooterCollection headersFooters = doc.FirstSection.HeadersFooters;
HeaderFooter footer = headersFooters[HeaderFooterType.FooterPrimary];

FindReplaceOptions options = new FindReplaceOptions
{
    MatchCase = false,
    FindWholeWordsOnly = false
};

int currentYear = DateTime.Now.Year;
footer.Range.Replace("(C) 2006 Aspose Pty Ltd.", $"Copyright (C) {currentYear} by Aspose Pty Ltd.", options);

doc.Save(ArtifactsDir + "HeaderFooter.ReplaceText.docx");
```

Показывает, как удалить все нижние колонтитулы из документа.

```csharp
Document doc = new Document(MyDir + "Header and footer types.docx");

// Перебираем каждый раздел и удаляем нижние колонтитулы всех видов.
foreach (Section section in doc.OfType<Section>())
{
    // Существует три типа нижнего и верхнего колонтитула.
    // 1 - «Первый» верхний/нижний колонтитул, который появляется только на первой странице раздела.
    HeaderFooter footer = section.HeadersFooters[HeaderFooterType.FooterFirst];
    footer?.Remove();

    // 2 - «Основной» верхний/нижний колонтитул, который появляется на нечетных страницах.
    footer = section.HeadersFooters[HeaderFooterType.FooterPrimary];
    footer?.Remove();

     // 3 - "Четный" верхний/нижний колонтитул, который появляется на четных страницах.
    footer = section.HeadersFooters[HeaderFooterType.FooterEven];
    footer?.Remove();

    Assert.AreEqual(0, section.HeadersFooters.Count(hf => !((HeaderFooter)hf).IsHeader));
}

doc.Save(ArtifactsDir + "HeaderFooter.RemoveFooters.docx");
```

### Смотрите также

* class [HeaderFooterCollection](../../headerfootercollection/)
* class [Section](../)
* пространство имен [Aspose.Words](../../section/)
* сборка [Aspose.Words](../../../)


