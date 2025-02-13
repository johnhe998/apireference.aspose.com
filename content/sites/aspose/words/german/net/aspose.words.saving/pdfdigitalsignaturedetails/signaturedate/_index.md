---
title: PdfDigitalSignatureDetails.SignatureDate
second_title: Aspose.Words für .NET-API-Referenz
description: PdfDigitalSignatureDetails eigendom. Ruft das Datum der Unterzeichnung ab oder setzt es.
type: docs
weight: 60
url: /de/net/aspose.words.saving/pdfdigitalsignaturedetails/signaturedate/
---
## PdfDigitalSignatureDetails.SignatureDate property

Ruft das Datum der Unterzeichnung ab oder setzt es.

```csharp
public DateTime SignatureDate { get; set; }
```

### Bemerkungen

Der Standardwert ist die aktuelle Uhrzeit.

Dieser Wert erscheint in der digitalen Signatur als unbestätigte Computerzeit.

### Beispiele

Zeigt, wie ein generiertes PDF-Dokument signiert wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Contents of signed PDF.");

CertificateHolder certificateHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

// Erstellen Sie ein "PdfSaveOptions"-Objekt, das wir an die "Save"-Methode des Dokuments übergeben können
// um zu ändern, wie diese Methode das Dokument in .PDF konvertiert.
PdfSaveOptions options = new PdfSaveOptions();

// Konfigurieren Sie das "DigitalSignatureDetails"-Objekt des "SaveOptions"-Objekts zu
// das Dokument digital signieren, während wir es mit der "Save"-Methode rendern.
DateTime signingTime = DateTime.Now;
options.DigitalSignatureDetails =
    new PdfDigitalSignatureDetails(certificateHolder, "Test Signing", "My Office", signingTime);
options.DigitalSignatureDetails.HashAlgorithm = PdfDigitalSignatureHashAlgorithm.Sha256;

Assert.AreEqual("Test Signing", options.DigitalSignatureDetails.Reason);
Assert.AreEqual("My Office", options.DigitalSignatureDetails.Location);
Assert.AreEqual(signingTime.ToUniversalTime(), options.DigitalSignatureDetails.SignatureDate.ToUniversalTime());

doc.Save(ArtifactsDir + "PdfSaveOptions.PdfDigitalSignature.pdf", options);
```

### Siehe auch

* class [PdfDigitalSignatureDetails](../)
* namensraum [Aspose.Words.Saving](../../pdfdigitalsignaturedetails/)
* Montage [Aspose.Words](../../../)


