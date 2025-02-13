---
title: Body.ParentSection
second_title: Справочник по API Aspose.Words для .NET
description: Body свойство. Получает родительский раздел этой истории.
type: docs
weight: 30
url: /ru/net/aspose.words/body/parentsection/
---
## Body.ParentSection property

Получает родительский раздел этой истории.

```csharp
public Section ParentSection { get; }
```

### Примечания

**Родительский раздел** эквивалентно`(Раздел)Родительский узел`.

### Примеры

Показывает, как сохранять концевые сноски в конце каждого раздела и изменять их положение.

```csharp
{
    Document doc = new Document();
    doc.RemoveAllChildren();

     // По умолчанию документ компилирует все концевые сноски в конце.
    Assert.AreEqual(EndnotePosition.EndOfDocument, doc.EndnoteOptions.Position);

    // Мы используем свойство "Position" объекта "EndnoteOptions" документа
     // вместо этого собирать концевые сноски в конце каждого раздела.
    doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;

    InsertSectionWithEndnote(doc, "Section 1", "Endnote 1, will stay in section 1");
    InsertSectionWithEndnote(doc, "Section 2", "Endnote 2, will be pushed down to section 3");
    InsertSectionWithEndnote(doc, "Section 3", "Endnote 3, will stay in section 3");

    // Получая разделы для отображения соответствующих концевых сносок, мы можем установить флаг «SuppressEndnotes»
    // объекта "PageSetup" раздела в "true", чтобы вернуться к поведению по умолчанию и передать его концевые сноски
    // в следующий раздел.
    PageSetup pageSetup = doc.Sections[1].PageSetup;
    pageSetup.SuppressEndnotes = true;

    doc.Save(ArtifactsDir + "PageSetup.SuppressEndnotes.docx");

/// <summary>
/// Добавляем к документу раздел с текстом и концевой сноской.
/// </summary>
private static void InsertSectionWithEndnote(Document doc, string sectionBodyText, string endnoteText)
{
    Section section = new Section(doc);

    doc.AppendChild(section);

    Body body = new Body(doc);
    section.AppendChild(body);

    Assert.AreEqual(section, body.ParentNode);

    Paragraph para = new Paragraph(doc);
    body.AppendChild(para);

    Assert.AreEqual(body, para.ParentNode);

    DocumentBuilder builder = new DocumentBuilder(doc);
    builder.MoveTo(para);
    builder.Write(sectionBodyText);
    builder.InsertFootnote(FootnoteType.Endnote, endnoteText);
}
```

### Смотрите также

* class [Section](../../section/)
* class [Body](../)
* пространство имен [Aspose.Words](../../body/)
* сборка [Aspose.Words](../../../)


