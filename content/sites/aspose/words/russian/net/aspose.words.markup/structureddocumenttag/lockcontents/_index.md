---
title: StructuredDocumentTag.LockContents
second_title: Справочник по API Aspose.Words для .NET
description: StructuredDocumentTag свойство. Если установлено значение true это свойство запрещает пользователю редактировать содержимое этого СДТ .
type: docs
weight: 200
url: /ru/net/aspose.words.markup/structureddocumenttag/lockcontents/
---
## StructuredDocumentTag.LockContents property

Если установлено значение true, это свойство запрещает пользователю редактировать содержимое этого **СДТ** .

```csharp
public bool LockContents { get; set; }
```

### Примеры

Показывает, как применять ограничения редактирования к тегам структурированного документа.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Вставьте простой текстовый структурированный тег документа, который действует как текстовое поле, которое предлагает пользователю заполнить его.
StructuredDocumentTag tag = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Inline);

// Установите для свойства LockContents значение true, чтобы запретить пользователю редактировать содержимое этого текстового поля.
tag.LockContents = true;
builder.Write("The contents of this structured document tag cannot be edited: ");
builder.InsertNode(tag);

tag = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Inline);

// Установите свойство «LockContentControl» в «true», чтобы запретить пользователю
// удаление этого тега структурированного документа вручную в Microsoft Word.
tag.LockContentControl = true;

builder.InsertParagraph();
builder.Write("This structured document tag cannot be deleted but its contents can be edited: ");
builder.InsertNode(tag);

doc.Save(ArtifactsDir + "StructuredDocumentTag.Lock.docx");
```

### Смотрите также

* class [StructuredDocumentTag](../)
* пространство имен [Aspose.Words.Markup](../../structureddocumenttag/)
* сборка [Aspose.Words](../../../)


