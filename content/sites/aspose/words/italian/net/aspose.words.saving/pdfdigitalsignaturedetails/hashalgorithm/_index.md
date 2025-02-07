---
title: PdfDigitalSignatureDetails.HashAlgorithm
second_title: Aspose.Words per .NET API Reference
description: PdfDigitalSignatureDetails proprietà. Ottiene o imposta lalgoritmo hash.
type: docs
weight: 30
url: /it/net/aspose.words.saving/pdfdigitalsignaturedetails/hashalgorithm/
---
## PdfDigitalSignatureDetails.HashAlgorithm property

Ottiene o imposta l'algoritmo hash.

```csharp
public PdfDigitalSignatureHashAlgorithm HashAlgorithm { get; set; }
```

### Osservazioni

Il valore predefinito è l'algoritmo SHA-256.

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

* enum [PdfDigitalSignatureHashAlgorithm](../../pdfdigitalsignaturehashalgorithm/)
* class [PdfDigitalSignatureDetails](../)
* spazio dei nomi [Aspose.Words.Saving](../../pdfdigitalsignaturedetails/)
* assemblea [Aspose.Words](../../../)


