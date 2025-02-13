---
title: MailMerge.CleanupParagraphsWithPunctuationMarks
second_title: Справочник по API Aspose.Words для .NET
description: MailMerge свойство. Получает или задает значение указывающее считаются ли абзацы со знаками препинания пустыми и должны ли они быть удалены еслиRemoveEmptyParagraphs опция указана.
type: docs
weight: 20
url: /ru/net/aspose.words.mailmerging/mailmerge/cleanupparagraphswithpunctuationmarks/
---
## MailMerge.CleanupParagraphsWithPunctuationMarks property

Получает или задает значение, указывающее, считаются ли абзацы со знаками препинания пустыми и должны ли они быть удалены, еслиRemoveEmptyParagraphs опция указана.

```csharp
public bool CleanupParagraphsWithPunctuationMarks { get; set; }
```

### Примечания

Значение по умолчанию:`истинный` .

Вот полный список очищаемых знаков препинания:

* !
* ,
* .
* :
* ;
* ?
* ¡
* ¿

### Примеры

Показывает, как удалить абзацы со знаками препинания после операции слияния.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

FieldMergeField mergeFieldOption1 = (FieldMergeField) builder.InsertField("MERGEFIELD", "Option_1");
mergeFieldOption1.FieldName = "Option_1";

builder.Write(punctuationMark);

FieldMergeField mergeFieldOption2 = (FieldMergeField) builder.InsertField("MERGEFIELD", "Option_2");
mergeFieldOption2.FieldName = "Option_2";

// Настройте свойство «CleanupOptions», чтобы удалить все пустые абзацы, которые создаст это слияние почты.
doc.MailMerge.CleanupOptions = MailMergeCleanupOptions.RemoveEmptyParagraphs;

// Установка для свойства "CleanupParagraphsWithPunctuationMarks" значения "true" также будет учитывать абзацы
// со знаками препинания пустыми, и операция слияния также удалит их.
// Установка для свойства "CleanupParagraphsWithPunctuationMarks" значения "false"
// удалит пустые абзацы, но не со знаками препинания.
// Это список знаков препинания, к которым относится это свойство: "!", ",", ".", ":", ";", "?", "¡", "¿".
doc.MailMerge.CleanupParagraphsWithPunctuationMarks = cleanupParagraphsWithPunctuationMarks;

doc.MailMerge.Execute(new[] { "Option_1", "Option_2" }, new object[] { null, null });

doc.Save(ArtifactsDir + "MailMerge.RemoveColonBetweenEmptyMergeFields.docx");
```

### Смотрите также

* class [MailMerge](../)
* пространство имен [Aspose.Words.MailMerging](../../mailmerge/)
* сборка [Aspose.Words](../../../)


