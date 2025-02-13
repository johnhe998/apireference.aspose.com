---
title: LoadOptions.Password
second_title: Referencia de API de Aspose.Words para .NET
description: LoadOptions propiedad. Obtiene o establece la contraseña para abrir un documento cifrado. Puede ser una cadena nula o vacía. El valor predeterminado es nulo.
type: docs
weight: 110
url: /es/net/aspose.words.loading/loadoptions/password/
---
## LoadOptions.Password property

Obtiene o establece la contraseña para abrir un documento cifrado. Puede ser una cadena nula o vacía. El valor predeterminado es nulo.

```csharp
public string Password { get; set; }
```

### Observaciones

Necesita saber la contraseña para abrir un documento encriptado. Si el documento no está encriptado, configúrelo como cadena nula o vacía.

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

* class [LoadOptions](../)
* espacio de nombres [Aspose.Words.Loading](../../loadoptions/)
* asamblea [Aspose.Words](../../../)


