---
title: Enum PdfDigitalSignatureHashAlgorithm
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Saving.PdfDigitalSignatureHashAlgorithm Sıralama. Dijital imza tarafından kullanılan bir dijital karma algoritmayı belirtir.
type: docs
weight: 5160
url: /tr/net/aspose.words.saving/pdfdigitalsignaturehashalgorithm/
---
## PdfDigitalSignatureHashAlgorithm enumeration

Dijital imza tarafından kullanılan bir dijital karma algoritmayı belirtir.

```csharp
public enum PdfDigitalSignatureHashAlgorithm
```

### değerler

| İsim | Değer | Tanım |
| --- | --- | --- |
| Sha256 | `0` | SHA-256 karma algoritması. |
| Sha384 | `1` | SHA-384 karma algoritması. |
| Sha512 | `2` | SHA-512 karma algoritması. |
| RipeMD160 | `3` | RIPEMD-160 karma algoritması. |

### Örnekler

Oluşturulan bir PDF belgesinin nasıl imzalanacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Contents of signed PDF.");

CertificateHolder certificateHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

// Belgenin "Kaydet" yöntemine aktarabileceğimiz bir "PdfSaveOptions" nesnesi oluşturun
// bu yöntemin belgeyi .PDF'ye dönüştürme şeklini değiştirmek için.
PdfSaveOptions options = new PdfSaveOptions();

// "SaveOptions" nesnesinin "DigitalSignatureDetails" nesnesini şu şekilde yapılandırın:
// "Kaydet" yöntemiyle belgeyi oluşturduğumuz gibi dijital olarak imzalıyoruz.
DateTime signingTime = DateTime.Now;
options.DigitalSignatureDetails =
    new PdfDigitalSignatureDetails(certificateHolder, "Test Signing", "My Office", signingTime);
options.DigitalSignatureDetails.HashAlgorithm = PdfDigitalSignatureHashAlgorithm.Sha256;

Assert.AreEqual("Test Signing", options.DigitalSignatureDetails.Reason);
Assert.AreEqual("My Office", options.DigitalSignatureDetails.Location);
Assert.AreEqual(signingTime.ToUniversalTime(), options.DigitalSignatureDetails.SignatureDate.ToUniversalTime());

doc.Save(ArtifactsDir + "PdfSaveOptions.PdfDigitalSignature.pdf", options);
```

### Ayrıca bakınız

* ad alanı [Aspose.Words.Saving](../../aspose.words.saving/)
* toplantı [Aspose.Words](../../)


