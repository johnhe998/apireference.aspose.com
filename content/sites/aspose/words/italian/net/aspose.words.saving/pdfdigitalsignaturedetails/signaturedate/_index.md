---
title: PdfDigitalSignatureDetails.SignatureDate
second_title: Aspose.Words per .NET API Reference
description: PdfDigitalSignatureDetails proprietà. Ottiene o imposta la data della firma.
type: docs
weight: 60
url: /it/net/aspose.words.saving/pdfdigitalsignaturedetails/signaturedate/
---
## PdfDigitalSignatureDetails.SignatureDate property

Ottiene o imposta la data della firma.

```csharp
public DateTime SignatureDate { get; set; }
```

### Osservazioni

Il valore predefinito è l'ora corrente.

Questo valore apparirà nella firma digitale come un'ora del computer non verificata.

### Esempi

Mostra come firmare un documento PDF generato.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Contents of signed PDF.");

CertificateHolder certificateHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

// Crea un oggetto "PdfSaveOptions" che possiamo passare al metodo "Save" del documento
// per modificare il modo in cui quel metodo converte il documento in .PDF.
PdfSaveOptions options = new PdfSaveOptions();

// Configura l'oggetto "DigitalSignatureDetails" dell'oggetto "SaveOptions" su
// Firma digitalmente il documento mentre lo eseguiamo con il metodo "Salva".
DateTime signingTime = DateTime.Now;
options.DigitalSignatureDetails =
    new PdfDigitalSignatureDetails(certificateHolder, "Test Signing", "My Office", signingTime);
options.DigitalSignatureDetails.HashAlgorithm = PdfDigitalSignatureHashAlgorithm.Sha256;

Assert.AreEqual("Test Signing", options.DigitalSignatureDetails.Reason);
Assert.AreEqual("My Office", options.DigitalSignatureDetails.Location);
Assert.AreEqual(signingTime.ToUniversalTime(), options.DigitalSignatureDetails.SignatureDate.ToUniversalTime());

doc.Save(ArtifactsDir + "PdfSaveOptions.PdfDigitalSignature.pdf", options);
```

### Guarda anche

* class [PdfDigitalSignatureDetails](../)
* spazio dei nomi [Aspose.Words.Saving](../../pdfdigitalsignaturedetails/)
* assemblea [Aspose.Words](../../../)


