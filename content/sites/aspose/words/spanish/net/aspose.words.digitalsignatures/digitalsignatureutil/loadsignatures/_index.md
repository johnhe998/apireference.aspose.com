---
title: DigitalSignatureUtil.LoadSignatures
second_title: Referencia de API de Aspose.Words para .NET
description: DigitalSignatureUtil método. Carga firmas digitales del documento.
type: docs
weight: 10
url: /es/net/aspose.words.digitalsignatures/digitalsignatureutil/loadsignatures/
---
## LoadSignatures(string) {#loadsignatures_1}

Carga firmas digitales del documento.

```csharp
public static DigitalSignatureCollection LoadSignatures(string fileName)
```

| Parámetro | Escribe | Descripción |
| --- | --- | --- |
| fileName | String | Ruta al documento. |

### Valor_devuelto

Recogida de firmas digitales. Devuelve una colección vacía si el archivo no está firmado.

### Ejemplos

Muestra cómo cargar firmas desde un documento firmado digitalmente.

```csharp
// Hay dos formas de cargar la colección de firmas digitales de un documento firmado utilizando la clase DigitalSignatureUtil.
// 1 - Cargar desde un documento desde un sistema de archivos local nombre de archivo:
DigitalSignatureCollection digitalSignatures = 
    DigitalSignatureUtil.LoadSignatures(MyDir + "Digitally signed.docx");

// Si esta colección no está vacía, entonces podemos verificar que el documento está firmado digitalmente.
Assert.AreEqual(1, digitalSignatures.Count);

// 2 - Cargar desde un documento desde un FileStream:
using (Stream stream = new FileStream(MyDir + "Digitally signed.docx", FileMode.Open))
{
    digitalSignatures = DigitalSignatureUtil.LoadSignatures(stream);
    Assert.AreEqual(1, digitalSignatures.Count);
}
```

Muestra cómo eliminar firmas digitales de un documento firmado digitalmente.

```csharp
// Hay dos formas de usar la clase DigitalSignatureUtil para eliminar firmas digitales
// de un documento firmado guardando una copia sin firmar en otro lugar del sistema de archivos local.
// 1 - Determine las ubicaciones tanto del documento firmado como de la copia sin firmar mediante cadenas de nombre de archivo:
DigitalSignatureUtil.RemoveAllSignatures(MyDir + "Digitally signed.docx",
    ArtifactsDir + "DigitalSignatureUtil.LoadAndRemove.FromString.docx");

// 2 - Determinar las ubicaciones tanto del documento firmado como de la copia sin firmar por secuencias de archivos:
using (Stream streamIn = new FileStream(MyDir + "Digitally signed.docx", FileMode.Open))
{
    using (Stream streamOut = new FileStream(ArtifactsDir + "DigitalSignatureUtil.LoadAndRemove.FromStream.docx", FileMode.Create))
    {
        DigitalSignatureUtil.RemoveAllSignatures(streamIn, streamOut);
    }
}

// Verifique que nuestros dos documentos de salida no tengan firmas digitales.
Assert.That(DigitalSignatureUtil.LoadSignatures(ArtifactsDir + "DigitalSignatureUtil.LoadAndRemove.FromString.docx"), Is.Empty);
Assert.That(DigitalSignatureUtil.LoadSignatures(ArtifactsDir + "DigitalSignatureUtil.LoadAndRemove.FromStream.docx"), Is.Empty);
```

### Ver también

* class [DigitalSignatureCollection](../../digitalsignaturecollection/)
* class [DigitalSignatureUtil](../)
* espacio de nombres [Aspose.Words.DigitalSignatures](../../digitalsignatureutil/)
* asamblea [Aspose.Words](../../../)

---

## LoadSignatures(Stream) {#loadsignatures}

Carga firmas digitales del documento usando stream.

```csharp
public static DigitalSignatureCollection LoadSignatures(Stream stream)
```

| Parámetro | Escribe | Descripción |
| --- | --- | --- |
| stream | Stream | Transmitir con el documento. |

### Valor_devuelto

Recogida de firmas digitales. Devuelve una colección vacía si el archivo no está firmado.

### Ejemplos

Muestra cómo cargar firmas desde un documento firmado digitalmente.

```csharp
// Hay dos formas de cargar la colección de firmas digitales de un documento firmado utilizando la clase DigitalSignatureUtil.
// 1 - Cargar desde un documento desde un sistema de archivos local nombre de archivo:
DigitalSignatureCollection digitalSignatures = 
    DigitalSignatureUtil.LoadSignatures(MyDir + "Digitally signed.docx");

// Si esta colección no está vacía, entonces podemos verificar que el documento está firmado digitalmente.
Assert.AreEqual(1, digitalSignatures.Count);

// 2 - Cargar desde un documento desde un FileStream:
using (Stream stream = new FileStream(MyDir + "Digitally signed.docx", FileMode.Open))
{
    digitalSignatures = DigitalSignatureUtil.LoadSignatures(stream);
    Assert.AreEqual(1, digitalSignatures.Count);
}
```

### Ver también

* class [DigitalSignatureCollection](../../digitalsignaturecollection/)
* class [DigitalSignatureUtil](../)
* espacio de nombres [Aspose.Words.DigitalSignatures](../../digitalsignatureutil/)
* asamblea [Aspose.Words](../../../)


