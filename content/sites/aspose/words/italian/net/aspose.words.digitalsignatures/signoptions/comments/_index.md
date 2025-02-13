---
title: SignOptions.Comments
second_title: Aspose.Words per .NET API Reference
description: SignOptions proprietà. Specifica i commenti sulla firma digitale. Il valore predefinito è stringa vuota Empty .
type: docs
weight: 20
url: /it/net/aspose.words.digitalsignatures/signoptions/comments/
---
## SignOptions.Comments property

Specifica i commenti sulla firma digitale. Il valore predefinito è **stringa vuota** (Empty ).

```csharp
public string Comments { get; set; }
```

### Esempi

Mostra come firmare digitalmente i documenti.

```csharp
// Crea un certificato X.509 da un archivio PKCS#12, che dovrebbe contenere una chiave privata.
CertificateHolder certificateHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

// Crea un commento e una data che verranno applicati con la nostra nuova firma digitale.
SignOptions signOptions = new SignOptions
{
    Comments = "My comment", 
    SignTime = DateTime.Now
};

// Prendi un documento non firmato dal file system locale tramite un flusso di file,
// quindi creane una copia firmata determinata dal nome del file del flusso di file di output.
using (Stream streamIn = new FileStream(MyDir + "Document.docx", FileMode.Open))
{
    using (Stream streamOut = new FileStream(ArtifactsDir + "DigitalSignatureUtil.SignDocument.docx", FileMode.OpenOrCreate))
    {
        DigitalSignatureUtil.Sign(streamIn, streamOut, certificateHolder, signOptions);
    }
}
```

### Guarda anche

* class [SignOptions](../)
* spazio dei nomi [Aspose.Words.DigitalSignatures](../../signoptions/)
* assemblea [Aspose.Words](../../../)


