---
title: Class DigitalSignatureCollection
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.DigitalSignatures.DigitalSignatureCollection clase. Proporciona una colección de solo lectura de firmas digitales adjuntas a un documento.
type: docs
weight: 380
url: /es/net/aspose.words.digitalsignatures/digitalsignaturecollection/
---
## DigitalSignatureCollection class

Proporciona una colección de solo lectura de firmas digitales adjuntas a un documento.

```csharp
public class DigitalSignatureCollection : IEnumerable<DigitalSignature>
```

## Constructores

| Nombre | Descripción |
| --- | --- |
| [DigitalSignatureCollection](digitalsignaturecollection/)() | Constructor predeterminado |

## Propiedades

| Nombre | Descripción |
| --- | --- |
| [Count](../../aspose.words.digitalsignatures/digitalsignaturecollection/count/) { get; } | Obtiene el número de elementos que contiene la colección. |
| [IsValid](../../aspose.words.digitalsignatures/digitalsignaturecollection/isvalid/) { get; } | Devoluciones`verdadero` si todas las firmas digitales de esta colección son válidas y el documento no ha sido manipulado También devuelve`verdadero`si no hay firmas digitales. Devuelve`falso` si al menos una firma digital no es válida. |
| [Item](../../aspose.words.digitalsignatures/digitalsignaturecollection/item/) { get; } | Obtiene una firma de documento en el índice especificado. |

## Métodos

| Nombre | Descripción |
| --- | --- |
| [GetEnumerator](../../aspose.words.digitalsignatures/digitalsignaturecollection/getenumerator/)() | Devuelve un objeto de enumerador de diccionario que se puede usar para iterar sobre todos los elementos de la colección. |

### Observaciones

[`DigitalSignatures`](../../aspose.words/document/digitalsignatures/)

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

Muestra cómo firmar documentos con certificados X.509.

```csharp
// Verifica que un documento no esté firmado.
Assert.False(FileFormatUtil.DetectFileFormat(MyDir + "Document.docx").HasDigitalSignature);

// Crear un objeto CertificateHolder a partir de un archivo PKCS12, que usaremos para firmar el documento.
CertificateHolder certificateHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw", null);

// Hay dos formas de guardar una copia firmada de un documento en el sistema de archivos local:
// 1 - Designar un documento por un nombre de archivo del sistema local y guardar una copia firmada en una ubicación especificada por otro nombre de archivo.
DigitalSignatureUtil.Sign(MyDir + "Document.docx", ArtifactsDir + "Document.DigitalSignature.docx", 
    certificateHolder, new SignOptions() { SignTime = DateTime.Now } );

Assert.True(FileFormatUtil.DetectFileFormat(ArtifactsDir + "Document.DigitalSignature.docx").HasDigitalSignature);

// 2 - Tome un documento de un flujo y guarde una copia firmada en otro flujo.
using (FileStream inDoc = new FileStream(MyDir + "Document.docx", FileMode.Open))
{
    using (FileStream outDoc = new FileStream(ArtifactsDir + "Document.DigitalSignature.docx", FileMode.Create))
    {
        DigitalSignatureUtil.Sign(inDoc, outDoc, certificateHolder);
    }
}

Assert.True(FileFormatUtil.DetectFileFormat(ArtifactsDir + "Document.DigitalSignature.docx").HasDigitalSignature);

// Verifique que todas las firmas digitales del documento sean válidas y verifique sus detalles.
Document signedDoc = new Document(ArtifactsDir + "Document.DigitalSignature.docx");
DigitalSignatureCollection digitalSignatureCollection = signedDoc.DigitalSignatures;

Assert.True(digitalSignatureCollection.IsValid);
Assert.AreEqual(1, digitalSignatureCollection.Count);
Assert.AreEqual(DigitalSignatureType.XmlDsig, digitalSignatureCollection[0].SignatureType);
Assert.AreEqual("CN=Morzal.Me", signedDoc.DigitalSignatures[0].IssuerName);
Assert.AreEqual("CN=Morzal.Me", signedDoc.DigitalSignatures[0].SubjectName);
```

### Ver también

* class [DigitalSignature](../digitalsignature/)
* espacio de nombres [Aspose.Words.DigitalSignatures](../../aspose.words.digitalsignatures/)
* asamblea [Aspose.Words](../../)


