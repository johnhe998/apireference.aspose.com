---
title: Class DigitalSignature
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.DigitalSignatures.DigitalSignature clase. Representa una firma digital en un documento y el resultado de su verificación.
type: docs
weight: 370
url: /es/net/aspose.words.digitalsignatures/digitalsignature/
---
## DigitalSignature class

Representa una firma digital en un documento y el resultado de su verificación.

```csharp
public class DigitalSignature
```

## Propiedades

| Nombre | Descripción |
| --- | --- |
| [CertificateHolder](../../aspose.words.digitalsignatures/digitalsignature/certificateholder/) { get; } | Devuelve el objeto del titular del certificado que contiene el certificado que se utilizó para firmar el documento. |
| [Comments](../../aspose.words.digitalsignatures/digitalsignature/comments/) { get; } | Obtiene el comentario de propósito de firma. |
| [IssuerName](../../aspose.words.digitalsignatures/digitalsignature/issuername/) { get; } | Devuelve el nombre distinguido del sujeto del emisor del certificado. |
| [IsValid](../../aspose.words.digitalsignatures/digitalsignature/isvalid/) { get; } | Devuelve verdadero si esta firma digital es válida y el documento no ha sido manipulado. |
| [SignatureType](../../aspose.words.digitalsignatures/digitalsignature/signaturetype/) { get; } | Obtiene el tipo de firma digital. |
| [SignTime](../../aspose.words.digitalsignatures/digitalsignature/signtime/) { get; } | Obtiene la hora a la que se firmó el documento. |
| [SubjectName](../../aspose.words.digitalsignatures/digitalsignature/subjectname/) { get; } | Devuelve el nombre distinguido del sujeto del certificado que se utilizó para firmar el documento. |

## Métodos

| Nombre | Descripción |
| --- | --- |
| override [ToString](../../aspose.words.digitalsignatures/digitalsignature/tostring/)() | Devuelve una cadena fácil de usar que muestra el valor de este objeto. |

### Ejemplos

Muestra cómo validar y mostrar información sobre cada firma en un documento.

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

### Ver también

* espacio de nombres [Aspose.Words.DigitalSignatures](../../aspose.words.digitalsignatures/)
* asamblea [Aspose.Words](../../)


