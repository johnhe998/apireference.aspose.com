---
title: Enum CompressionLevel
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Saving.CompressionLevel enumeración. Nivel de compresión para archivos OOXML.
type: docs
weight: 4610
url: /es/net/aspose.words.saving/compressionlevel/
---
## CompressionLevel enumeration

Nivel de compresión para archivos OOXML.

(los archivos DOCX y DOTX son internamente un archivo ZIP, esta propiedad controla el nivel de compresión del archivo.

Tenga en cuenta que el archivo FlatOpc no es un archivo ZIP, por lo tanto, esta propiedad no afecta a los archivos FlatOpc.)

```csharp
public enum CompressionLevel
```

### Valores

| Nombre | Valor | Descripción |
| --- | --- | --- |
| Normal | `0` | Nivel de compresión normal. Nivel de compresión predeterminado utilizado por Aspose.Words. |
| Maximum | `1` | Nivel máximo de compresión. |
| Fast | `2` | Nivel de compresión rápido. |
| SuperFast | `3` | Nivel de compresión súper rápido. Microsoft Word usa este nivel de compresión. |

### Ejemplos

Muestra cómo especificar el nivel de compresión que se utilizará al guardar un documento OOXML.

```csharp
Document doc = new Document(MyDir + "Big document.docx");

// Cuando guardamos el documento en formato OOXML, podemos crear un objeto OoxmlSaveOptions
// y luego pasarlo al método de guardado del documento para modificar cómo guardamos el documento.
// Establezca la propiedad "CompressionLevel" en "CompressionLevel.Maximum" para aplicar la compresión más fuerte y más lenta.
// Establecer la propiedad "CompressionLevel" en "CompressionLevel.Normal" para aplicar
// la compresión predeterminada que usa Aspose.Words al guardar documentos OOXML.
// Establezca la propiedad "CompressionLevel" en "CompressionLevel.Fast" para aplicar una compresión más rápida y más débil.
// Establecer la propiedad "CompressionLevel" en "CompressionLevel.SuperFast" para aplicar
// la compresión predeterminada que usa Microsoft Word.
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx);
saveOptions.CompressionLevel = compressionLevel;

Stopwatch st = Stopwatch.StartNew();
doc.Save(ArtifactsDir + "OoxmlSaveOptions.DocumentCompression.docx", saveOptions);
st.Stop();

FileInfo fileInfo = new FileInfo(ArtifactsDir + "OoxmlSaveOptions.DocumentCompression.docx");

Console.WriteLine($"Saving operation done using the \"{compressionLevel}\" compression level:");
Console.WriteLine($"\tDuration:\t{st.ElapsedMilliseconds} ms");
Console.WriteLine($"\tFile Size:\t{fileInfo.Length} bytes");
```

### Ver también

* espacio de nombres [Aspose.Words.Saving](../../aspose.words.saving/)
* asamblea [Aspose.Words](../../)


