---
title: PdfDigitalSignatureDetails.SignatureDate
second_title: Справочник по API Aspose.Words для .NET
description: PdfDigitalSignatureDetails свойство. Получает или задает дату подписания.
type: docs
weight: 60
url: /ru/net/aspose.words.saving/pdfdigitalsignaturedetails/signaturedate/
---
## PdfDigitalSignatureDetails.SignatureDate property

Получает или задает дату подписания.

```csharp
public DateTime SignatureDate { get; set; }
```

### Примечания

Значение по умолчанию — текущее время.

Это значение появится в цифровой подписи как непроверенное компьютерное время.

### Примеры

Показывает, как подписать сгенерированный PDF-документ.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Contents of signed PDF.");

CertificateHolder certificateHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

// Создаем объект "PdfSaveOptions", который мы можем передать в метод "Сохранить" документа
// для изменения того, как этот метод преобразует документ в .PDF.
PdfSaveOptions options = new PdfSaveOptions();

// Настройте объект "DigitalSignatureDetails" объекта "SaveOptions" на
// подписать документ цифровой подписью, когда мы визуализируем его, с помощью метода «Сохранить».
DateTime signingTime = DateTime.Now;
options.DigitalSignatureDetails =
    new PdfDigitalSignatureDetails(certificateHolder, "Test Signing", "My Office", signingTime);
options.DigitalSignatureDetails.HashAlgorithm = PdfDigitalSignatureHashAlgorithm.Sha256;

Assert.AreEqual("Test Signing", options.DigitalSignatureDetails.Reason);
Assert.AreEqual("My Office", options.DigitalSignatureDetails.Location);
Assert.AreEqual(signingTime.ToUniversalTime(), options.DigitalSignatureDetails.SignatureDate.ToUniversalTime());

doc.Save(ArtifactsDir + "PdfSaveOptions.PdfDigitalSignature.pdf", options);
```

### Смотрите также

* class [PdfDigitalSignatureDetails](../)
* пространство имен [Aspose.Words.Saving](../../pdfdigitalsignaturedetails/)
* сборка [Aspose.Words](../../../)


