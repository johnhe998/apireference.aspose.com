---
title: SignOptions.ProviderId
second_title: Aspose.Words für .NET-API-Referenz
description: SignOptions eigendom. Gibt die KlassenID des Signaturanbieters an. Standardwert ist Leer nur Nullen Guid .
type: docs
weight: 40
url: /de/net/aspose.words.digitalsignatures/signoptions/providerid/
---
## SignOptions.ProviderId property

Gibt die Klassen-ID des Signaturanbieters an. Standardwert ist **Leer (nur Nullen) Guid** .

```csharp
public Guid ProviderId { get; set; }
```

### Bemerkungen

Der Cryptographic Service Provider (CSP) ist ein unabhängiges Softwaremodul, das eigentlich Kryptografiealgorithmen zur Authentifizierung, Kodierung und Verschlüsselung ausführt. MS Office reserviert den Wert von {00000000-0000-0000-0000-000000000000} für seinen standardmäßigen Signaturanbieter.

Die GUID des zusätzlich installierten Providers entnehmen Sie bitte der mitgelieferten Dokumentation des Providers.

Darüber hinaus werden alle installierten Kryptografieanbieter in der Windows-Registrierung aufgeführt. Sie finden sie im folgenden Pfad: HKLM\SOFTWARE\Microsoft\Cryptography\Defaults\Provider. Es gibt einen Schlüsselnamen, der "CP Service UUID" entspricht eine GUID des Signaturanbieters.

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

* class [SignOptions](../)
* namensraum [Aspose.Words.DigitalSignatures](../../signoptions/)
* Montage [Aspose.Words](../../../)


