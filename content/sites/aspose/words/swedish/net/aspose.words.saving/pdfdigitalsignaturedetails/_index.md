---
title: Class PdfDigitalSignatureDetails
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.Saving.PdfDigitalSignatureDetails klass. Innehåller detaljer för att signera ett PDFdokument med en digital signatur.
type: docs
weight: 5150
url: /sv/net/aspose.words.saving/pdfdigitalsignaturedetails/
---
## PdfDigitalSignatureDetails class

Innehåller detaljer för att signera ett PDF-dokument med en digital signatur.

```csharp
public class PdfDigitalSignatureDetails
```

## Konstruktörer

| namn | Beskrivning |
| --- | --- |
| [PdfDigitalSignatureDetails](pdfdigitalsignaturedetails/#constructor)() | Initierar en instans av denna klass. |
| [PdfDigitalSignatureDetails](pdfdigitalsignaturedetails/#constructor_1)(CertificateHolder, string, string, DateTime) | Initierar en instans av denna klass. |

## Egenskaper

| namn | Beskrivning |
| --- | --- |
| [CertificateHolder](../../aspose.words.saving/pdfdigitalsignaturedetails/certificateholder/) { get; set; } | Returnerar certifikatinnehavarens objekt som innehåller certifikatet som användes för att signera dokumentet. |
| [HashAlgorithm](../../aspose.words.saving/pdfdigitalsignaturedetails/hashalgorithm/) { get; set; } | Hämtar eller ställer in hash-algoritmen. |
| [Location](../../aspose.words.saving/pdfdigitalsignaturedetails/location/) { get; set; } | Hämtar eller ställer in platsen för signeringen. |
| [Reason](../../aspose.words.saving/pdfdigitalsignaturedetails/reason/) { get; set; } | Hämtar eller anger orsaken till signeringen. |
| [SignatureDate](../../aspose.words.saving/pdfdigitalsignaturedetails/signaturedate/) { get; set; } | Hämtar eller ställer in datumet för signeringen. |
| [TimestampSettings](../../aspose.words.saving/pdfdigitalsignaturedetails/timestampsettings/) { get; set; } | Hämtar eller ställer in tidsstämpelinställningarna för digital signatur. |

### Anmärkningar

För närvarande är digital signering av PDF-dokument endast tillgängligt på .NET 2.0 eller senare.

För att digitalt signera ett PDF-dokument när det skapas av Aspose.Words, ställ in[`DigitalSignatureDetails`](../pdfsaveoptions/digitalsignaturedetails/) egenskap till en giltig`PdfDigitalSignatureDetails` objekt och spara sedan dokumentet i PDF-format genom att passera the[`PdfSaveOptions`](../pdfsaveoptions/)som en parameter i[`Save`](../../aspose.words/document/save/) metod.

Aspose.Words skapar en PKCS#7-signatur över hela PDF-dokumentet och använder "Adobe.PPKMS"-filtret och "adbe.pkcs7.sha1"-underfiltret när man skapar en digital signatur.

### Exempel

Visar hur man signerar ett genererat PDF-dokument.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Contents of signed PDF.");

CertificateHolder certificateHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

// Skapa ett "PdfSaveOptions"-objekt som vi kan skicka till dokumentets "Spara"-metod
// för att ändra hur den metoden konverterar dokumentet till .PDF.
PdfSaveOptions options = new PdfSaveOptions();

// Konfigurera "DigitalSignatureDetails"-objektet för "SaveOptions"-objektet till
// signera dokumentet digitalt när vi renderar det med "Spara"-metoden.
DateTime signingTime = DateTime.Now;
options.DigitalSignatureDetails =
    new PdfDigitalSignatureDetails(certificateHolder, "Test Signing", "My Office", signingTime);
options.DigitalSignatureDetails.HashAlgorithm = PdfDigitalSignatureHashAlgorithm.Sha256;

Assert.AreEqual("Test Signing", options.DigitalSignatureDetails.Reason);
Assert.AreEqual("My Office", options.DigitalSignatureDetails.Location);
Assert.AreEqual(signingTime.ToUniversalTime(), options.DigitalSignatureDetails.SignatureDate.ToUniversalTime());

doc.Save(ArtifactsDir + "PdfSaveOptions.PdfDigitalSignature.pdf", options);
```

### Se även

* namnutrymme [Aspose.Words.Saving](../../aspose.words.saving/)
* hopsättning [Aspose.Words](../../)


