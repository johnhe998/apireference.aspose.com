---
title: FieldToc.UpdatePageNumbers
second_title: Справочник по API Aspose.Words для .NET
description: FieldToc метод. Обновляет номера страниц для элементов в этом оглавлении.
type: docs
weight: 180
url: /ru/net/aspose.words.fields/fieldtoc/updatepagenumbers/
---
## FieldToc.UpdatePageNumbers method

Обновляет номера страниц для элементов в этом оглавлении.

```csharp
public bool UpdatePageNumbers()
```

### Возвращаемое значение

Истинно, если операция прошла успешно. Если какая-либо из связанных закладок TOC была удалена, будет возвращено значение false.

### Примеры

Показывает, как вставить оглавление и заполнить его записями на основе стилей заголовков.

```csharp
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.StartBookmark("MyBookmark");

    // Вставьте поле TOC, которое объединит все заголовки в оглавление.
    // Для каждого заголовка это поле создаст строку с текстом в этом стиле заголовка слева,
    // и страница, на которой появляется заголовок справа.
    FieldToc field = (FieldToc)builder.InsertField(FieldType.FieldTOC, true);

    // Используйте свойство BookmarkName, чтобы отображать только заголовки
    // которые появляются в пределах закладки с именем "MyBookmark".
    field.BookmarkName = "MyBookmark";

    // Текст со встроенным стилем заголовка, например "Заголовок 1", примененный к нему, будет считаться заголовком.
    // Мы можем назвать дополнительные стили, которые будут выбраны в качестве заголовков оглавлением в этом свойстве, и их уровни оглавления.
    field.CustomStyles = "Quote; 6; Intense Quote; 7";

    // По умолчанию уровни Styles/TOC разделяются в свойстве CustomStyles запятой,
    // но мы можем установить собственный разделитель в этом свойстве.
    doc.FieldOptions.CustomTocStyleSeparator = ";";

    // Настройте поле, чтобы исключить любые заголовки, уровни TOC которых выходят за пределы этого диапазона.
    field.HeadingLevelRange = "1-3";

    // В оглавлении не будут отображаться номера страниц заголовков, уровни оглавления которых находятся в этом диапазоне.
    field.PageNumberOmittingLevelRange = "2-5";

     // Установите пользовательскую строку, которая будет отделять каждый заголовок от его номера страницы.
    field.EntrySeparator = "-";
    field.InsertHyperlinks = true;
    field.HideInWebLayout = false;
    field.PreserveLineBreaks = true;
    field.PreserveTabs = true;
    field.UseParagraphOutlineLevel = false;

    InsertNewPageWithHeading(builder, "First entry", "Heading 1");
    builder.Writeln("Paragraph text.");
    InsertNewPageWithHeading(builder, "Second entry", "Heading 1");
    InsertNewPageWithHeading(builder, "Third entry", "Quote");
    InsertNewPageWithHeading(builder, "Fourth entry", "Intense Quote");

    // В этих двух заголовках номера страниц будут опущены, поскольку они находятся в диапазоне "2-5".
    InsertNewPageWithHeading(builder, "Fifth entry", "Heading 2");
    InsertNewPageWithHeading(builder, "Sixth entry", "Heading 3");

    // Эта запись не появляется, потому что "Заголовок 4" находится за пределами диапазона "1-3", который мы установили ранее.
    InsertNewPageWithHeading(builder, "Seventh entry", "Heading 4");

    builder.EndBookmark("MyBookmark");
    builder.Writeln("Paragraph text.");

    // Эта запись не отображается, потому что она находится за пределами закладки, указанной в оглавлении.
    InsertNewPageWithHeading(builder, "Eighth entry", "Heading 1");

    Assert.AreEqual(" TOC  \\b MyBookmark \\t \"Quote; 6; Intense Quote; 7\" \\o 1-3 \\n 2-5 \\p - \\h \\x \\w", field.GetFieldCode());

    field.UpdatePageNumbers();
    doc.UpdateFields();
    doc.Save(ArtifactsDir + "Field.TOC.docx");

/// <summary>
/// Начать новую страницу и вставить абзац указанного стиля.
/// </summary>
public void InsertNewPageWithHeading(DocumentBuilder builder, string captionText, string styleName)
{
    builder.InsertBreak(BreakType.PageBreak);
    string originalStyle = builder.ParagraphFormat.StyleName;
    builder.ParagraphFormat.Style = builder.Document.Styles[styleName];
    builder.Writeln(captionText);
    builder.ParagraphFormat.Style = builder.Document.Styles[originalStyle];
}
```

### Смотрите также

* class [FieldToc](../)
* пространство имен [Aspose.Words.Fields](../../fieldtoc/)
* сборка [Aspose.Words](../../../)


