---
title: Class PdfEncryptionDetails
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Saving.PdfEncryptionDetails сорт. Содержит сведения о шифровании и разрешениях на доступ к PDFдокументу.
type: docs
weight: 5180
url: /ru/net/aspose.words.saving/pdfencryptiondetails/
---
## PdfEncryptionDetails class

Содержит сведения о шифровании и разрешениях на доступ к PDF-документу.

```csharp
public class PdfEncryptionDetails
```

## Конструкторы

| Имя | Описание |
| --- | --- |
| [PdfEncryptionDetails](pdfencryptiondetails/)(string, string) | Инициализирует экземпляр этого класса. |

## Характеристики

| Имя | Описание |
| --- | --- |
| [OwnerPassword](../../aspose.words.saving/pdfencryptiondetails/ownerpassword/) { get; set; } | Указывает пароль владельца для зашифрованного PDF-документа. |
| [Permissions](../../aspose.words.saving/pdfencryptiondetails/permissions/) { get; set; } | Определяет операции, разрешенные пользователю с зашифрованным PDF-документом. Значение по умолчанию:DisallowAll . |
| [UserPassword](../../aspose.words.saving/pdfencryptiondetails/userpassword/) { get; set; } | Указывает пароль пользователя, необходимый для открытия зашифрованного PDF-документа. |

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

* пространство имен [Aspose.Words.Saving](../../aspose.words.saving/)
* сборка [Aspose.Words](../../)


