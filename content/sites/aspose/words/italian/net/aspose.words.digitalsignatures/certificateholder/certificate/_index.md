---
title: CertificateHolder.Certificate
second_title: Aspose.Words per .NET API Reference
description: CertificateHolder proprietà. Restituisce listanza di Certificato X5092 che contiene chiavi private pubbliche e catena di certificati.
type: docs
weight: 20
url: /it/net/aspose.words.digitalsignatures/certificateholder/certificate/
---
## CertificateHolder.Certificate property

Restituisce l'istanza di **Certificato X5092** che contiene chiavi private, pubbliche e catena di certificati.

```csharp
public X509Certificate2 Certificate { get; }
```

### Valore di ritorno

X509Certificate2 esempio

### Esempi

Mostra come convalidare e visualizzare le informazioni su ciascuna firma in un documento.

```csharp
Document doc = new Document(MyDir + "Digitally signed.docx");

foreach (DigitalSignature signature in doc.DigitalSignatures)
{
    Console.WriteLine($"{(signature.IsValid ? "Valid" : "Invalid")} signature: ");
    Console.WriteLine($"\tReason:\t{signature.Comments}"); 
    Console.WriteLine($"\tType:\t{signature.SignatureType}");
    Console.WriteLine($"\tSign time:\t{signature.SignTime}");
    Console.WriteLine($"\tSubject name:\t{signature.CertificateHolder.Certificate.SubjectName}");
    Console.WriteLine($"\tIssuer name:\t{signature.CertificateHolder.Certificate.IssuerName.Name}");
    Console.WriteLine();
}
```

### Guarda anche

* class [CertificateHolder](../)
* spazio dei nomi [Aspose.Words.DigitalSignatures](../../certificateholder/)
* assemblea [Aspose.Words](../../../)


