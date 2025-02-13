---
title: Class WriteProtection
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Settings.WriteProtection сорт. Указывает параметры защиты от записи для документа.
type: docs
weight: 5670
url: /ru/net/aspose.words.settings/writeprotection/
---
## WriteProtection class

Указывает параметры защиты от записи для документа.

```csharp
public class WriteProtection
```

## Характеристики

| Имя | Описание |
| --- | --- |
| [IsWriteProtected](../../aspose.words.settings/writeprotection/iswriteprotected/) { get; } | Возвращает true, если установлен пароль защиты от записи. |
| [ReadOnlyRecommended](../../aspose.words.settings/writeprotection/readonlyrecommended/) { get; set; } | Указывает, рекомендовал ли автор документа открывать документ только для чтения. |

## Методы

| Имя | Описание |
| --- | --- |
| [SetPassword](../../aspose.words.settings/writeprotection/setpassword/)(string) | Устанавливает пароль защиты от записи для документа. |
| [ValidatePassword](../../aspose.words.settings/writeprotection/validatepassword/)(string) | Возвращает true, если указанный пароль совпадает с паролем защиты от записи, которым был защищен документ. Если документ не защищен паролем от записи, возвращает false. |

### Примечания

Защита от записи указывает, рекомендовал ли автор открывать документ только для чтения и/или требовать пароль для изменения документа.

Защита от записи отличается от защиты документа. Защита от записи указана в Microsoft Word в параметрах диалогового окна Сохранить как.

Вы не создаете экземпляры этого класса напрямую. Вы получаете доступ к настройкам защиты документов через[`WriteProtection`](../../aspose.words/document/writeprotection/) имущество.

### Примеры

Показывает, как защитить документ паролем.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world! This document is protected.");

// Введите пароль длиной до 15 символов, а затем проверьте статус защиты документа.
doc.WriteProtection.SetPassword("MyPassword");
doc.WriteProtection.ReadOnlyRecommended = true;

Assert.IsTrue(doc.WriteProtection.IsWriteProtected);
Assert.IsTrue(doc.WriteProtection.ValidatePassword("MyPassword"));

// Защита не препятствует программному редактированию документа и не шифрует содержимое.
doc.Save(ArtifactsDir + "Document.WriteProtection.docx");
doc = new Document(ArtifactsDir + "Document.WriteProtection.docx");

Assert.IsTrue(doc.WriteProtection.IsWriteProtected);

builder = new DocumentBuilder(doc);
builder.MoveToDocumentEnd();
builder.Writeln("Writing text in a protected document.");

Assert.AreEqual("Hello world! This document is protected." +
                "\rWriting text in a protected document.", doc.GetText().Trim());
```

### Смотрите также

* пространство имен [Aspose.Words.Settings](../../aspose.words.settings/)
* сборка [Aspose.Words](../../)


