---
title: FieldNoteRef.InsertRelativePosition
second_title: Справочник по API Aspose.Words для .NET
description: FieldNoteRef свойство. Получает или задает следует ли вставлять относительное положение отмеченного закладкой абзаца.
type: docs
weight: 50
url: /ru/net/aspose.words.fields/fieldnoteref/insertrelativeposition/
---
## FieldNoteRef.InsertRelativePosition property

Получает или задает, следует ли вставлять относительное положение отмеченного закладкой абзаца.

```csharp
public bool InsertRelativePosition { get; set; }
```

### Примеры

Показывает, как вставить поля NOTEREF и изменить их внешний вид.

```csharp
public void FieldNoteRef()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    // Создать закладку со сноской, на которую будет ссылаться поле NOTEREF.
    InsertBookmarkWithFootnote(builder, "MyBookmark1", "Contents of MyBookmark1", "Footnote from MyBookmark1");

    // В этом поле NOTEREF будет отображаться номер сноски внутри указанной закладки.
    // Установка свойства InsertHyperlink позволяет нам перейти к закладке, нажав Ctrl + щелкнув поле в Microsoft Word.
    Assert.AreEqual(" NOTEREF  MyBookmark2 \\h",
        InsertFieldNoteRef(builder, "MyBookmark2", true, false, false, "Hyperlink to Bookmark2, with footnote number ").GetFieldCode());

    // При использовании флага \p после номера сноски в поле также отображается положение закладки относительно поля.
    // Bookmark1 находится над этим полем и содержит сноску номер 1, поэтому при обновлении результатом будет «1 выше».
    Assert.AreEqual(" NOTEREF  MyBookmark1 \\h \\p",
        InsertFieldNoteRef(builder, "MyBookmark1", true, true, false, "Bookmark1, with footnote number ").GetFieldCode());

    // Закладка2 находится под этим полем и содержит сноску номер 2, поэтому в поле будет отображаться «2 ниже».
    // Флаг \f заставляет цифру 2 отображаться в том же формате, что и метка номера сноски в реальном тексте.
    Assert.AreEqual(" NOTEREF  MyBookmark2 \\h \\p \\f",
        InsertFieldNoteRef(builder, "MyBookmark2", true, true, true, "Bookmark2, with footnote number ").GetFieldCode());

    builder.InsertBreak(BreakType.PageBreak);
    InsertBookmarkWithFootnote(builder, "MyBookmark2", "Contents of MyBookmark2", "Footnote from MyBookmark2");

    doc.UpdateFields();
    doc.Save(ArtifactsDir + "Field.NOTEREF.docx");

/// <summary>
/// Использует конструктор документов для вставки поля NOTEREF с указанными свойствами.
/// </summary>
private static FieldNoteRef InsertFieldNoteRef(DocumentBuilder builder, string bookmarkName, bool insertHyperlink, bool insertRelativePosition, bool insertReferenceMark, string textBefore)
{
    builder.Write(textBefore);

    FieldNoteRef field = (FieldNoteRef)builder.InsertField(FieldType.FieldNoteRef, true);
    field.BookmarkName = bookmarkName;
    field.InsertHyperlink = insertHyperlink;
    field.InsertRelativePosition = insertRelativePosition;
    field.InsertReferenceMark = insertReferenceMark;
    builder.Writeln();

    return field;
}

/// <summary>
/// Использует конструктор документов для вставки именованной закладки со сноской в конце.
/// </summary>
private static void InsertBookmarkWithFootnote(DocumentBuilder builder, string bookmarkName, string bookmarkText, string footnoteText)
{
    builder.StartBookmark(bookmarkName);
    builder.Write(bookmarkText);
    builder.InsertFootnote(FootnoteType.Footnote, footnoteText);
    builder.EndBookmark(bookmarkName);
    builder.Writeln();
}
```

### Смотрите также

* class [FieldNoteRef](../)
* пространство имен [Aspose.Words.Fields](../../fieldnoteref/)
* сборка [Aspose.Words](../../../)


