---
title: PdfDigitalSignatureDetails.SignatureDate
linktitle: SignatureDate
articleTitle: SignatureDate
second_title: Aspose.Words for .NET
description: PdfDigitalSignatureDetails SignatureDate property. Gets or sets the date of the signing in C#.
type: docs
weight: 60
url: /net/aspose.words.saving/pdfdigitalsignaturedetails/signaturedate/
---
## PdfDigitalSignatureDetails.SignatureDate property

Gets or sets the date of the signing.

```csharp
public DateTime SignatureDate { get; set; }
```

## Remarks

The default value is the current time.

This value will appear in the digital signature as an unverified computer time.

## Examples

Shows how to sign a generated PDF document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Contents of signed PDF.");

CertificateHolder certificateHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

// Create a "PdfSaveOptions" object that we can pass to the document's "Save" method
// to modify how that method converts the document to .PDF.
PdfSaveOptions options = new PdfSaveOptions();

// Configure the "DigitalSignatureDetails" object of the "SaveOptions" object to
// digitally sign the document as we render it with the "Save" method.
DateTime signingTime = DateTime.Now;
options.DigitalSignatureDetails =
    new PdfDigitalSignatureDetails(certificateHolder, "Test Signing", "My Office", signingTime);
options.DigitalSignatureDetails.HashAlgorithm = PdfDigitalSignatureHashAlgorithm.RipeMD160;

Assert.AreEqual("Test Signing", options.DigitalSignatureDetails.Reason);
Assert.AreEqual("My Office", options.DigitalSignatureDetails.Location);
Assert.AreEqual(signingTime.ToUniversalTime(), options.DigitalSignatureDetails.SignatureDate.ToUniversalTime());

doc.Save(ArtifactsDir + "PdfSaveOptions.PdfDigitalSignature.pdf", options);
```

### See Also

* class [PdfDigitalSignatureDetails](../)
* namespace [Aspose.Words.Saving](../../../aspose.words.saving/)
* assembly [Aspose.Words](../../../)
