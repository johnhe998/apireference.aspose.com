---
title: Enum DocumentSecurity
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Properties.DocumentSecurity перечисление. Используется как значение дляSecurity property. Указывает уровень безопасности документа в виде числового значения.
type: docs
weight: 4240
url: /ru/net/aspose.words.properties/documentsecurity/
---
## DocumentSecurity enumeration

Используется как значение для[`Security`](../builtindocumentproperties/security/) property. Указывает уровень безопасности документа в виде числового значения.

```csharp
[Flags]
public enum DocumentSecurity
```

### Ценности

| Имя | Ценность | Описание |
| --- | --- | --- |
| None | `0` | Свойство не указывает состояния безопасности. |
| PasswordProtected | `1` | Документ защищен паролем. (Примечание никогда не встречалось в документе). |
| ReadOnlyRecommended | `2` | Документ, по возможности открываемый только для чтения, но этот параметр можно переопределить. |
| ReadOnlyEnforced | `4` | Документ всегда должен открываться только для чтения. |
| ReadOnlyExceptAnnotations | `8` | Документ всегда должен открываться только для чтения, кроме аннотаций. |

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

* пространство имен [Aspose.Words.Properties](../../aspose.words.properties/)
* сборка [Aspose.Words](../../)


