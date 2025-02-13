---
title: Class DigitalSignature
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.DigitalSignatures.DigitalSignature classe. Rappresenta una firma digitale su un documento e il risultato della sua verifica.
type: docs
weight: 370
url: /it/net/aspose.words.digitalsignatures/digitalsignature/
---
## DigitalSignature class

Rappresenta una firma digitale su un documento e il risultato della sua verifica.

```csharp
public class DigitalSignature
```

## Proprietà

| Nome | Descrizione |
| --- | --- |
| [CertificateHolder](../../aspose.words.digitalsignatures/digitalsignature/certificateholder/) { get; } | Restituisce l'oggetto titolare del certificato che contiene il certificato utilizzato per firmare il documento. |
| [Comments](../../aspose.words.digitalsignatures/digitalsignature/comments/) { get; } | Ottiene il commento sullo scopo della firma. |
| [IssuerName](../../aspose.words.digitalsignatures/digitalsignature/issuername/) { get; } | Restituisce il nome distinto del soggetto dell'emittente del certificato. |
| [IsValid](../../aspose.words.digitalsignatures/digitalsignature/isvalid/) { get; } | Restituisce vero se questa firma digitale è valida e il documento non è stato manomesso. |
| [SignatureType](../../aspose.words.digitalsignatures/digitalsignature/signaturetype/) { get; } | Ottiene il tipo della firma digitale. |
| [SignTime](../../aspose.words.digitalsignatures/digitalsignature/signtime/) { get; } | Ottiene l'ora in cui il documento è stato firmato. |
| [SubjectName](../../aspose.words.digitalsignatures/digitalsignature/subjectname/) { get; } | Restituisce il nome distinto dell'oggetto del certificato utilizzato per firmare il documento. |

## Metodi

| Nome | Descrizione |
| --- | --- |
| override [ToString](../../aspose.words.digitalsignatures/digitalsignature/tostring/)() | Restituisce una stringa intuitiva che visualizza il valore di questo oggetto. |

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

* spazio dei nomi [Aspose.Words.DigitalSignatures](../../aspose.words.digitalsignatures/)
* assemblea [Aspose.Words](../../)


