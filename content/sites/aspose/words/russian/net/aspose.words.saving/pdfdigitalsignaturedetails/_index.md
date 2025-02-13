---
title: Class PdfDigitalSignatureDetails
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Saving.PdfDigitalSignatureDetails сорт. Содержит сведения о подписании документа PDF цифровой подписью.
type: docs
weight: 5150
url: /ru/net/aspose.words.saving/pdfdigitalsignaturedetails/
---
## PdfDigitalSignatureDetails class

Содержит сведения о подписании документа PDF цифровой подписью.

```csharp
public class PdfDigitalSignatureDetails
```

## Конструкторы

| Имя | Описание |
| --- | --- |
| [PdfDigitalSignatureDetails](pdfdigitalsignaturedetails/#constructor)() | Инициализирует экземпляр этого класса. |
| [PdfDigitalSignatureDetails](pdfdigitalsignaturedetails/#constructor_1)(CertificateHolder, string, string, DateTime) | Инициализирует экземпляр этого класса. |

## Характеристики

| Имя | Описание |
| --- | --- |
| [CertificateHolder](../../aspose.words.saving/pdfdigitalsignaturedetails/certificateholder/) { get; set; } | Возвращает объект держателя сертификата, содержащий сертификат, который использовался для подписи документа. |
| [HashAlgorithm](../../aspose.words.saving/pdfdigitalsignaturedetails/hashalgorithm/) { get; set; } | Получает или задает алгоритм хеширования. |
| [Location](../../aspose.words.saving/pdfdigitalsignaturedetails/location/) { get; set; } | Получает или задает расположение подписи. |
| [Reason](../../aspose.words.saving/pdfdigitalsignaturedetails/reason/) { get; set; } | Получает или задает причину подписания. |
| [SignatureDate](../../aspose.words.saving/pdfdigitalsignaturedetails/signaturedate/) { get; set; } | Получает или задает дату подписания. |
| [TimestampSettings](../../aspose.words.saving/pdfdigitalsignaturedetails/timestampsettings/) { get; set; } | Получает или задает параметры временной метки цифровой подписи. |

### Примечания

В настоящее время цифровая подпись PDF-документов доступна только в .NET 2.0 или более поздней версии.

Чтобы подписать PDF-документ цифровой подписью при его создании с помощью Aspose.Words, установите[`DigitalSignatureDetails`](../pdfsaveoptions/digitalsignaturedetails/) на допустимое`PdfDigitalSignatureDetails` объект, а затем сохраните документ в формате PDF, передав [`PdfSaveOptions`](../pdfsaveoptions/)как параметр в[`Save`](../../aspose.words/document/save/) метод.

Aspose.Words создает подпись PKCS#7 для всего документа PDF и использует фильтр «Adobe.PPKMS» и подфильтр «adbe.pkcs7.sha1» при создании цифровой подписи.

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

* пространство имен [Aspose.Words.Saving](../../aspose.words.saving/)
* сборка [Aspose.Words](../../)


