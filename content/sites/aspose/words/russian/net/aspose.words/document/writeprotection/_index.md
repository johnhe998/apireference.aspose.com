---
title: Document.WriteProtection
second_title: Справочник по API Aspose.Words для .NET
description: Document свойство. Предоставляет доступ к параметрам защиты документа от записи.
type: docs
weight: 480
url: /ru/net/aspose.words/document/writeprotection/
---
## Document.WriteProtection property

Предоставляет доступ к параметрам защиты документа от записи.

```csharp
public WriteProtection WriteProtection { get; }
```

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

* class [WriteProtection](../../../aspose.words.settings/writeprotection/)
* class [Document](../)
* пространство имен [Aspose.Words](../../document/)
* сборка [Aspose.Words](../../../)


