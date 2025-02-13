---
title: SignOptions.ProviderId
second_title: Aspose.Words per .NET API Reference
description: SignOptions proprietà. Specifica lID classe del provider di firma. Il valore predefinito è Vuoto tutti zeri Guid .
type: docs
weight: 40
url: /it/net/aspose.words.digitalsignatures/signoptions/providerid/
---
## SignOptions.ProviderId property

Specifica l'ID classe del provider di firma. Il valore predefinito è **Vuoto (tutti zeri) Guid** .

```csharp
public Guid ProviderId { get; set; }
```

### Osservazioni

Il provider di servizi di crittografia (CSP) è un modulo software indipendente che esegue effettivamente algoritmi di crittografia per l'autenticazione, la codifica e la crittografia. MS Office riserva il valore di {00000000-0000-0000-0000-000000000000} per il provider di firma predefinito.

Il GUID del provider installato in aggiunta deve essere ottenuto dalla documentazione fornita con il provider.

Inoltre, tutti i provider di crittografia installati sono enumerati nel registro di Windows. Può essere trovato nel seguente percorso: HKLM\SOFTWARE\Microsoft\Cryptography\Defaults\Provider. C'è un nome chiave "CP Service UUID" che corrisponde a un GUID del provider di firma.

### Esempi

Mostra come firmare un documento con un certificato personale e una riga di firma.

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

// Riapri il nostro documento salvato e verifica che le proprietà "IsSigned" e "IsValid" siano entrambe "true",
// indicando che la riga della firma contiene una firma.
doc = new Document(ArtifactsDir + "DocumentBuilder.SignatureLineProviderId.Signed.docx");
Shape shape = (Shape)doc.GetChild(NodeType.Shape, 0, true);
signatureLine = shape.SignatureLine;

Assert.True(signatureLine.IsSigned);
Assert.True(signatureLine.IsValid);
```

### Guarda anche

* class [SignOptions](../)
* spazio dei nomi [Aspose.Words.DigitalSignatures](../../signoptions/)
* assemblea [Aspose.Words](../../../)


