---
title: SignatureLineOptions.Email
second_title: Aspose.Words für .NET-API-Referenz
description: SignatureLineOptions eigendom. Ruft die EMailAdresse des vorgeschlagenen Unterzeichners ab oder legt sie fest. Der Standardwert für diese Eigenschaft ist leerer String Empty .
type: docs
weight: 40
url: /de/net/aspose.words/signaturelineoptions/email/
---
## SignatureLineOptions.Email property

Ruft die E-Mail-Adresse des vorgeschlagenen Unterzeichners ab oder legt sie fest. Der Standardwert für diese Eigenschaft ist **leerer String** (Empty ).

```csharp
public string Email { get; set; }
```

### Beispiele

Zeigt, wie ein Dokument mit einem persönlichen Zertifikat und einer Signaturzeile signiert wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

SignatureLineOptions signatureLineOptions = new SignatureLineOptions
{
    Signer = "vderyushev",
    SignerTitle = "QA",
    Email = "vderyushev@aspose.com",
    ShowDate = true,
    DefaultInstructions = false,
    Instructions = "Please sign here.",
    AllowComments = true
};

SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");

Assert.False(signatureLine.IsSigned);
Assert.False(signatureLine.IsValid);

doc.Save(ArtifactsDir + "DocumentBuilder.SignatureLineProviderId.docx");

SignOptions signOptions = new SignOptions
{
    SignatureLineId = signatureLine.Id,
    ProviderId = signatureLine.ProviderId,
    Comments = "Document was signed by vderyushev",
    SignTime = DateTime.Now
};

CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(ArtifactsDir + "DocumentBuilder.SignatureLineProviderId.docx", 
    ArtifactsDir + "DocumentBuilder.SignatureLineProviderId.Signed.docx", certHolder, signOptions);

// Öffnen Sie unser gespeichertes Dokument erneut und überprüfen Sie, ob die Eigenschaften "IsSigned" und "IsValid" beide gleich "true" sind,
// zeigt an, dass die Signaturzeile eine Signatur enthält.
doc = new Document(ArtifactsDir + "DocumentBuilder.SignatureLineProviderId.Signed.docx");
Shape shape = (Shape)doc.GetChild(NodeType.Shape, 0, true);
signatureLine = shape.SignatureLine;

Assert.True(signatureLine.IsSigned);
Assert.True(signatureLine.IsValid);
```

### Siehe auch

* class [SignatureLineOptions](../)
* namensraum [Aspose.Words](../../signaturelineoptions/)
* Montage [Aspose.Words](../../../)


