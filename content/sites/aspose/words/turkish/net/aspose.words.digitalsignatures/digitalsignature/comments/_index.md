---
title: DigitalSignature.Comments
second_title: Aspose.Words for .NET API Referansı
description: DigitalSignature mülk. İmzalama amacı yorumunu alır.
type: docs
weight: 20
url: /tr/net/aspose.words.digitalsignatures/digitalsignature/comments/
---
## DigitalSignature.Comments property

İmzalama amacı yorumunu alır.

```csharp
public string Comments { get; }
```

### Örnekler

Bir belgedeki her imzayla ilgili bilgilerin nasıl doğrulanacağını ve görüntüleneceğini gösterir.

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

### Ayrıca bakınız

* class [DigitalSignature](../)
* ad alanı [Aspose.Words.DigitalSignatures](../../digitalsignature/)
* toplantı [Aspose.Words](../../../)


