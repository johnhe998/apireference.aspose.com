---
title: DigitalSignature.SignTime
second_title: Référence de l'API Aspose.Words pour .NET
description: DigitalSignature propriété. Obtient lheure à laquelle le document a été signé.
type: docs
weight: 60
url: /fr/net/aspose.words.digitalsignatures/digitalsignature/signtime/
---
## DigitalSignature.SignTime property

Obtient l'heure à laquelle le document a été signé.

```csharp
public DateTime SignTime { get; }
```

### Exemples

Montre comment valider et afficher des informations sur chaque signature dans un document.

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

### Voir également

* class [DigitalSignature](../)
* espace de noms [Aspose.Words.DigitalSignatures](../../digitalsignature/)
* Assemblée [Aspose.Words](../../../)


