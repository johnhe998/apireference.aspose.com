---
title: PdfDigitalSignatureDetails.PdfDigitalSignatureDetails
second_title: Aspose.Words for .NET API Referansı
description: PdfDigitalSignatureDetails inşaatçı. Bu sınıfın bir örneğini başlatır.
type: docs
weight: 10
url: /tr/net/aspose.words.saving/pdfdigitalsignaturedetails/pdfdigitalsignaturedetails/
---
## PdfDigitalSignatureDetails() {#constructor}

Bu sınıfın bir örneğini başlatır.

```csharp
public PdfDigitalSignatureDetails()
```

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

* class [PdfDigitalSignatureDetails](../)
* ad alanı [Aspose.Words.Saving](../../pdfdigitalsignaturedetails/)
* toplantı [Aspose.Words](../../../)

---

## PdfDigitalSignatureDetails(CertificateHolder, string, string, DateTime) {#constructor_1}

Bu sınıfın bir örneğini başlatır.

```csharp
public PdfDigitalSignatureDetails(CertificateHolder certificateHolder, string reason, 
    string location, DateTime signatureDate)
```

| Parametre | Tip | Tanım |
| --- | --- | --- |
| certificateHolder | CertificateHolder | Sertifikanın kendisini içeren sertifika sahibi. |
| reason | String | İmzalama nedeni. |
| location | String | İmza yeri. |
| signatureDate | DateTime | İmza tarihi ve saati. |

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

* class [CertificateHolder](../../../aspose.words.digitalsignatures/certificateholder/)
* class [PdfDigitalSignatureDetails](../)
* ad alanı [Aspose.Words.Saving](../../pdfdigitalsignaturedetails/)
* toplantı [Aspose.Words](../../../)


