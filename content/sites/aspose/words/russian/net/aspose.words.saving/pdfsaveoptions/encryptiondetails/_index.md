---
title: PdfSaveOptions.EncryptionDetails
second_title: Справочник по API Aspose.Words для .NET
description: PdfSaveOptions свойство. Получает или задает данные для шифрования выходного PDFдокумента.
type: docs
weight: 110
url: /ru/net/aspose.words.saving/pdfsaveoptions/encryptiondetails/
---
## PdfSaveOptions.EncryptionDetails property

Получает или задает данные для шифрования выходного PDF-документа.

```csharp
public PdfEncryptionDetails EncryptionDetails { get; set; }
```

### Примечания

Значение по умолчанию равно null, и выходной документ не будет зашифрован. Если для этого свойства задано допустимое значение[`PdfEncryptionDetails`](../../pdfencryptiondetails/) object, , то выходной PDF-документ будет зашифрован.

Алгоритм шифрования AES-128 используется при сохранении в формате PDF 1.7 (включая PDF/UA-1). Алгоритм шифрования AES-256 используется при сохранении в формате PDF 2.0.

Шифрование запрещено соответствием PDF/A. Этот параметр будет игнорироваться при сохранении в PDF/A.

ContentCopyForAccessibilityразрешение требуется соответствием PDF/UA , если выходной документ зашифрован. Это разрешение будет автоматически использоваться при сохранении в PDF/UA.

ContentCopyForAccessibility разрешение устарело в формате PDF 2.0. Это разрешение будет игнорироваться при сохранении в PDF 2.0.

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

* class [PdfEncryptionDetails](../../pdfencryptiondetails/)
* class [PdfSaveOptions](../)
* пространство имен [Aspose.Words.Saving](../../pdfsaveoptions/)
* сборка [Aspose.Words](../../../)


