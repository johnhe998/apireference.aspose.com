---
title: DigitalSignature.SignatureType
second_title: Aspose.Words för .NET API Referens
description: DigitalSignature fast egendom. Hämtar typen av digital signatur.
type: docs
weight: 50
url: /sv/net/aspose.words.digitalsignatures/digitalsignature/signaturetype/
---
## DigitalSignature.SignatureType property

Hämtar typen av digital signatur.

```csharp
public DigitalSignatureType SignatureType { get; }
```

### Exempel

Visar hur man validerar och visar information om varje signatur i ett dokument.

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

### Se även

* enum [DigitalSignatureType](../../digitalsignaturetype/)
* class [DigitalSignature](../)
* namnutrymme [Aspose.Words.DigitalSignatures](../../digitalsignature/)
* hopsättning [Aspose.Words](../../../)


