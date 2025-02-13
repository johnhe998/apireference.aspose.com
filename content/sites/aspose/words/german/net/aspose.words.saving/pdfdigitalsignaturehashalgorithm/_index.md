---
title: Enum PdfDigitalSignatureHashAlgorithm
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Saving.PdfDigitalSignatureHashAlgorithm opsomming. Gibt einen digitalen HashAlgorithmus an der von einer digitalen Signatur verwendet wird.
type: docs
weight: 5160
url: /de/net/aspose.words.saving/pdfdigitalsignaturehashalgorithm/
---
## PdfDigitalSignatureHashAlgorithm enumeration

Gibt einen digitalen Hash-Algorithmus an, der von einer digitalen Signatur verwendet wird.

```csharp
public enum PdfDigitalSignatureHashAlgorithm
```

### Werte

| Name | Wert | Beschreibung |
| --- | --- | --- |
| Sha256 | `0` | SHA-256-Hash-Algorithmus. |
| Sha384 | `1` | SHA-384-Hash-Algorithmus. |
| Sha512 | `2` | SHA-512-Hash-Algorithmus. |
| RipeMD160 | `3` | RIPEMD-160-Hash-Algorithmus. |

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

* namensraum [Aspose.Words.Saving](../../aspose.words.saving/)
* Montage [Aspose.Words](../../)


