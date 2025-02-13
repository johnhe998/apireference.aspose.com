---
title: BuiltInDocumentProperties.Security
second_title: Справочник по API Aspose.Words для .NET
description: BuiltInDocumentProperties свойство. Задает уровень безопасности документа в виде числового значения.
type: docs
weight: 250
url: /ru/net/aspose.words.properties/builtindocumentproperties/security/
---
## BuiltInDocumentProperties.Security property

Задает уровень безопасности документа в виде числового значения.

```csharp
public DocumentSecurity Security { get; set; }
```

### Примечания

Используйте это свойство только в информационных целях, поскольку Microsoft Word не всегда задает это свойство. Это свойство доступно только в документах DOC и OOXML.

Чтобы защитить или снять защиту с документа, используйте the [`Protect`](../../../aspose.words/document/protect/) а также[`Unprotect`](../../../aspose.words/document/unprotect/)методы.

Aspose.Words обновляет это свойство до правильного значения перед сохранением документа.

### Примеры

Показывает, как использовать свойства документа для отображения уровня безопасности документа.

```csharp
Document doc = new Document();

Assert.AreEqual(DocumentSecurity.None, doc.BuiltInDocumentProperties.Security);

// Если мы настроим документ только для чтения, он будет отображать этот статус с помощью встроенного свойства «Безопасность».
doc.WriteProtection.ReadOnlyRecommended = true;
doc.Save(ArtifactsDir + "DocumentProperties.Security.ReadOnlyRecommended.docx");

Assert.AreEqual(DocumentSecurity.ReadOnlyRecommended, 
    new Document(ArtifactsDir + "DocumentProperties.Security.ReadOnlyRecommended.docx").BuiltInDocumentProperties.Security);

// Защитите документ от записи, а затем проверьте его уровень безопасности.
doc = new Document();

Assert.False(doc.WriteProtection.IsWriteProtected);

doc.WriteProtection.SetPassword("MyPassword");

Assert.True(doc.WriteProtection.ValidatePassword("MyPassword"));
Assert.True(doc.WriteProtection.IsWriteProtected);

doc.Save(ArtifactsDir + "DocumentProperties.Security.ReadOnlyEnforced.docx");

Assert.AreEqual(DocumentSecurity.ReadOnlyEnforced,
    new Document(ArtifactsDir + "DocumentProperties.Security.ReadOnlyEnforced.docx").BuiltInDocumentProperties.Security);

// «Безопасность» — это описательное свойство. Мы можем отредактировать его значение вручную.
doc = new Document();

doc.Protect(ProtectionType.AllowOnlyComments, "MyPassword");
doc.BuiltInDocumentProperties.Security = DocumentSecurity.ReadOnlyExceptAnnotations;
doc.Save(ArtifactsDir + "DocumentProperties.Security.ReadOnlyExceptAnnotations.docx");

Assert.AreEqual(DocumentSecurity.ReadOnlyExceptAnnotations,
    new Document(ArtifactsDir + "DocumentProperties.Security.ReadOnlyExceptAnnotations.docx").BuiltInDocumentProperties.Security);
```

### Смотрите также

* enum [DocumentSecurity](../../documentsecurity/)
* class [BuiltInDocumentProperties](../)
* пространство имен [Aspose.Words.Properties](../../builtindocumentproperties/)
* сборка [Aspose.Words](../../../)


