---
title: PdfSaveOptions.DigitalSignatureDetails
second_title: Справочник по API Aspose.Words для .NET
description: PdfSaveOptions свойство. Получает или задает сведения для подписания выходного PDFдокумента.
type: docs
weight: 60
url: /ru/net/aspose.words.saving/pdfsaveoptions/digitalsignaturedetails/
---
## PdfSaveOptions.DigitalSignatureDetails property

Получает или задает сведения для подписания выходного PDF-документа.

```csharp
public PdfDigitalSignatureDetails DigitalSignatureDetails { get; set; }
```

### Примечания

Значение по умолчанию равно null, и выходной документ не будет подписан. Если для этого свойства задано допустимое значение[`PdfDigitalSignatureDetails`](../../pdfdigitalsignaturedetails/) object, , то выходной PDF-документ будет иметь цифровую подпись.

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

* class [PdfDigitalSignatureDetails](../../pdfdigitalsignaturedetails/)
* class [PdfSaveOptions](../)
* пространство имен [Aspose.Words.Saving](../../pdfsaveoptions/)
* сборка [Aspose.Words](../../../)


