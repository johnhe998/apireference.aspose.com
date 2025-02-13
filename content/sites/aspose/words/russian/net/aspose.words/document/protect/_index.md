---
title: Document.Protect
second_title: Справочник по API Aspose.Words для .NET
description: Document метод. Защищает документ от изменений без изменения существующего пароля или назначает случайный пароль.
type: docs
weight: 630
url: /ru/net/aspose.words/document/protect/
---
## Protect(ProtectionType) {#protect}

Защищает документ от изменений без изменения существующего пароля или назначает случайный пароль.

```csharp
public void Protect(ProtectionType type)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| type | ProtectionType | Указывает тип защиты документа. |

### Примечания

Когда документ защищен, пользователь может вносить только ограниченные изменения, , такие как добавление аннотаций, внесение изменений или заполнение формы.

Когда вы защищаете документ, и документ уже имеет пароль защиты, существующий пароль защиты не изменяется.

Когда вы защищаете документ, и документ не имеет пароля защиты, этот метод назначает случайный пароль, который делает невозможным снятие защиты документа в Microsoft Word, но вы все равно можете снять защиту документа в Aspose.Words, поскольку это не требовать пароль при снятии защиты.

### Примеры

Показывает, как отключить защиту для раздела.

```csharp
Document doc = new Document();

DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Section 1. Hello world!");
builder.InsertBreak(BreakType.SectionBreakNewPage);

builder.Writeln("Section 2. Hello again!");
builder.Write("Please enter text here: ");
builder.InsertTextInput("TextInput1", TextFormFieldType.Regular, "", "Placeholder text", 0);

// Применить защиту от записи к каждому разделу в документе.
doc.Protect(ProtectionType.AllowOnlyFormFields);

// Отключаем защиту от записи для первой секции.
doc.Sections[0].ProtectedForForms = false;

// В этом выходном документе мы сможем свободно редактировать первый раздел,
// и мы сможем редактировать содержимое поля формы только во втором разделе.
doc.Save(ArtifactsDir + "Section.Protect.docx");
```

### Смотрите также

* enum [ProtectionType](../../protectiontype/)
* class [Document](../)
* пространство имен [Aspose.Words](../../document/)
* сборка [Aspose.Words](../../../)

---

## Protect(ProtectionType, string) {#protect_1}

Защищает документ от изменений и дополнительно устанавливает пароль защиты.

```csharp
public void Protect(ProtectionType type, string password)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| type | ProtectionType | Указывает тип защиты документа. |
| password | String | Пароль для защиты документа с помощью . Укажите null или пустую строку, если вы хотите защитить документ без пароля. |

### Примечания

Когда документ защищен, пользователь может вносить только ограниченные изменения, , такие как добавление аннотаций, внесение изменений или заполнение формы.

Обратите внимание, что защита документа отличается от защиты от записи. Защита от записи задается с помощью[`WriteProtection`](../writeprotection/).

### Примеры

Показывает, как защитить и снять защиту с документа.

```csharp
Document doc = new Document();
doc.Protect(ProtectionType.ReadOnly, "password");

Assert.AreEqual(ProtectionType.ReadOnly, doc.ProtectionType);

// Если мы откроем этот документ в Microsoft Word, намереваясь его отредактировать,
// нам нужно будет применить пароль, чтобы пройти защиту.
doc.Save(ArtifactsDir + "Document.Protect.docx");

// Обратите внимание, что защита распространяется только на пользователей Microsoft Word, открывающих наш документ.
// Мы никак не зашифровали документ, и нам не нужен пароль, чтобы открыть и отредактировать его программно.
Document protectedDoc = new Document(ArtifactsDir + "Document.Protect.docx");

Assert.AreEqual(ProtectionType.ReadOnly, protectedDoc.ProtectionType);

DocumentBuilder builder = new DocumentBuilder(protectedDoc);
builder.Writeln("Text added to a protected document.");
// Есть два способа снять защиту с документа.
// 1 - Без пароля:
doc.Unprotect();

Assert.AreEqual(ProtectionType.NoProtection, doc.ProtectionType);

doc.Protect(ProtectionType.ReadOnly, "NewPassword");

Assert.AreEqual(ProtectionType.ReadOnly, doc.ProtectionType);

doc.Unprotect("WrongPassword");

Assert.AreEqual(ProtectionType.ReadOnly, doc.ProtectionType);

// 2 - С правильным паролем:
doc.Unprotect("NewPassword");

Assert.AreEqual(ProtectionType.NoProtection, doc.ProtectionType);
```

### Смотрите также

* enum [ProtectionType](../../protectiontype/)
* class [Document](../)
* пространство имен [Aspose.Words](../../document/)
* сборка [Aspose.Words](../../../)


