---
title: FieldCitation.Suffix
second_title: Справочник по API Aspose.Words для .NET
description: FieldCitation свойство. Получает или задает суффикс который добавляется к цитате.
type: docs
weight: 70
url: /ru/net/aspose.words.fields/fieldcitation/suffix/
---
## FieldCitation.Suffix property

Получает или задает суффикс, который добавляется к цитате.

```csharp
public string Suffix { get; set; }
```

### Примеры

Показывает, как работать с полями ЦИТАЦИЯ и БИБЛИОГРАФИЯ.

```csharp
// Открываем документ, содержащий библиографические источники, которые мы можем найти в
// Microsoft Word через ссылки -> Цитаты и ссылки Библиография -> Управление источниками.
Document doc = new Document(MyDir + "Bibliography.docx");
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Text to be cited with one source.");

// Создать цитату, указав только номер страницы и автора книги, на которую ссылаются.
FieldCitation fieldCitation = (FieldCitation)builder.InsertField(FieldType.FieldCitation, true);

// Мы ссылаемся на источники, используя имена их тегов.
fieldCitation.SourceTag = "Book1";
fieldCitation.PageNumber = "85";
fieldCitation.SuppressAuthor = false;
fieldCitation.SuppressTitle = true;
fieldCitation.SuppressYear = true;

Assert.AreEqual(" CITATION  Book1 \\p 85 \\t \\y", fieldCitation.GetFieldCode());

// Создать более подробную цитату со ссылкой на два источника.
builder.InsertParagraph();
builder.Write("Text to be cited with two sources.");
fieldCitation = (FieldCitation)builder.InsertField(FieldType.FieldCitation, true);
fieldCitation.SourceTag = "Book1";
fieldCitation.AnotherSourceTag = "Book2";
fieldCitation.FormatLanguageId = "en-US";
fieldCitation.PageNumber = "19";
fieldCitation.Prefix = "Prefix ";
fieldCitation.Suffix = " Suffix";
fieldCitation.SuppressAuthor = false;
fieldCitation.SuppressTitle = false;
fieldCitation.SuppressYear = false;
fieldCitation.VolumeNumber = "VII";

Assert.AreEqual(" CITATION  Book1 \\m Book2 \\l en-US \\p 19 \\f \"Prefix \" \\s \" Suffix\" \\v VII", fieldCitation.GetFieldCode());

// Мы можем использовать поле БИБЛИОГРАФИЯ для отображения всех источников в документе.
builder.InsertBreak(BreakType.PageBreak);
FieldBibliography fieldBibliography = (FieldBibliography)builder.InsertField(FieldType.FieldBibliography, true);
fieldBibliography.FormatLanguageId = "1124";

Assert.AreEqual(" BIBLIOGRAPHY  \\l 1124", fieldBibliography.GetFieldCode());

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.CITATION.docx");
```

### Смотрите также

* class [FieldCitation](../)
* пространство имен [Aspose.Words.Fields](../../fieldcitation/)
* сборка [Aspose.Words](../../../)


