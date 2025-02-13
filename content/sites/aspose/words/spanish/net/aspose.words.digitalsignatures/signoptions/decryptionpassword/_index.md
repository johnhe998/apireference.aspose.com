---
title: SignOptions.DecryptionPassword
second_title: Referencia de API de Aspose.Words para .NET
description: SignOptions propiedad. La contraseña para descifrar el documento de origen. El valor predeterminado es cuerda vacía Empty .
type: docs
weight: 30
url: /es/net/aspose.words.digitalsignatures/signoptions/decryptionpassword/
---
## SignOptions.DecryptionPassword property

La contraseña para descifrar el documento de origen. El valor predeterminado es **cuerda vacía** (Empty ).

```csharp
public string DecryptionPassword { get; set; }
```

### Observaciones

Si el documento OOXML está cifrado, debe proporcionar la contraseña de descifrado para descifrar el documento de origen antes de que se firme. Esto no es necesario para los documentos en formato DOC binario.

### Ejemplos

Muestra cómo firmar un archivo de documento cifrado.

```csharp
// Cree un certificado X.509 desde un almacén PKCS#12, que debe contener una clave privada.
CertificateHolder certificateHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

// Cree un comentario, fecha y contraseña de descifrado que se aplicará con nuestra nueva firma digital.
SignOptions signOptions = new SignOptions
{
    Comments = "Comment",
    SignTime = DateTime.Now,
    DecryptionPassword = "docPassword"
};

// Establecer un nombre de archivo del sistema local para el documento de entrada sin firmar y un nombre de archivo de salida para su nueva copia firmada digitalmente.
string inputFileName = MyDir + "Encrypted.docx";
string outputFileName = ArtifactsDir + "DigitalSignatureUtil.DecryptionPassword.docx";

DigitalSignatureUtil.Sign(inputFileName, outputFileName, certificateHolder, signOptions);
```

### Ver también

* class [SignOptions](../)
* espacio de nombres [Aspose.Words.DigitalSignatures](../../signoptions/)
* asamblea [Aspose.Words](../../../)


