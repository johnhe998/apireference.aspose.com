---
title: DigitalSignature.IsValid
second_title: Référence de l'API Aspose.Words pour .NET
description: DigitalSignature propriété. Renvoie vrai si cette signature numérique est valide et que le document na pas été falsifié.
type: docs
weight: 40
url: /fr/net/aspose.words.digitalsignatures/digitalsignature/isvalid/
---
## DigitalSignature.IsValid property

Renvoie vrai si cette signature numérique est valide et que le document n'a pas été falsifié.

```csharp
public bool IsValid { get; }
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


