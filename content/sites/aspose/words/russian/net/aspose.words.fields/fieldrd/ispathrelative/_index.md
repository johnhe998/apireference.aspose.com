---
title: FieldRD.IsPathRelative
second_title: Справочник по API Aspose.Words для .NET
description: FieldRD свойство. Получает или задает является ли путь относительным к текущему документу.
type: docs
weight: 30
url: /ru/net/aspose.words.fields/fieldrd/ispathrelative/
---
## FieldRD.IsPathRelative property

Получает или задает, является ли путь относительным к текущему документу.

```csharp
public bool IsPathRelative { get; set; }
```

### Примеры

Показывает использование поля RD для создания записей оглавления из заголовков в других документах.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Используйте конструктор документов, чтобы вставить оглавление,
// и затем добавьте одну запись для оглавления на следующей странице.
builder.InsertField(FieldType.FieldTOC, true);
builder.InsertBreak(BreakType.PageBreak);
builder.CurrentParagraph.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("TOC entry from within this document");

// Вставьте поле RD, которое ссылается на другой документ локальной файловой системы в его свойстве FileName.
// Оглавление также теперь будет принимать все заголовки из документа, на который ссылаются, в качестве записей для своей таблицы.
FieldRD field = (FieldRD)builder.InsertField(FieldType.FieldRefDoc, true);
field.FileName = "ReferencedDocument.docx";
field.IsPathRelative = true;

Assert.AreEqual(" RD  ReferencedDocument.docx \\f", field.GetFieldCode());

 // Создайте документ, на который ссылается поле RD, и вставьте заголовок.
// Этот заголовок будет отображаться как запись в поле TOC в нашем первом документе.
Document referencedDoc = new Document();
DocumentBuilder refDocBuilder = new DocumentBuilder(referencedDoc);
refDocBuilder.CurrentParagraph.ParagraphFormat.StyleName = "Heading 1";
refDocBuilder.Writeln("TOC entry from referenced document");
referencedDoc.Save(ArtifactsDir + "ReferencedDocument.docx");

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.RD.docx");
```

### Смотрите также

* class [FieldRD](../)
* пространство имен [Aspose.Words.Fields](../../fieldrd/)
* сборка [Aspose.Words](../../../)


