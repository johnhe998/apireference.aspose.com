---
title: PdfEncryptionDetails.Permissions
second_title: Справочник по API Aspose.Words для .NET
description: PdfEncryptionDetails свойство. Определяет операции разрешенные пользователю с зашифрованным PDFдокументом. Значение по умолчаниюDisallowAll .
type: docs
weight: 30
url: /ru/net/aspose.words.saving/pdfencryptiondetails/permissions/
---
## PdfEncryptionDetails.Permissions property

Определяет операции, разрешенные пользователю с зашифрованным PDF-документом. Значение по умолчанию:DisallowAll .

```csharp
public PdfPermissions Permissions { get; set; }
```

### Примеры

Показывает, как установить разрешения для сохраненного документа PDF.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Hello world!");

PdfEncryptionDetails encryptionDetails =
    new PdfEncryptionDetails("password", string.Empty);

// Начните с запрета всех разрешений.
encryptionDetails.Permissions = PdfPermissions.DisallowAll;

// Расширить права, чтобы разрешить редактирование аннотаций.
encryptionDetails.Permissions = PdfPermissions.ModifyAnnotations | PdfPermissions.DocumentAssembly;

// Создаем объект "PdfSaveOptions", который мы можем передать в метод "Сохранить" документа
// для изменения того, как этот метод преобразует документ в .PDF.
PdfSaveOptions saveOptions = new PdfSaveOptions();

// Включить шифрование через свойство EncryptionDetails.
saveOptions.EncryptionDetails = encryptionDetails;

// Когда мы откроем этот документ, нам нужно будет указать пароль, прежде чем получить доступ к его содержимому.
doc.Save(ArtifactsDir + "PdfSaveOptions.EncryptionPermissions.pdf", saveOptions);
```

### Смотрите также

* enum [PdfPermissions](../../pdfpermissions/)
* class [PdfEncryptionDetails](../)
* пространство имен [Aspose.Words.Saving](../../pdfencryptiondetails/)
* сборка [Aspose.Words](../../../)


