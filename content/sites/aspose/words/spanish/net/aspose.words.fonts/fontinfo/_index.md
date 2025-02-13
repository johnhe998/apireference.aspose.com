---
title: Class FontInfo
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Fonts.FontInfo clase. Especifica información sobre una fuente utilizada en el documento.
type: docs
weight: 2740
url: /es/net/aspose.words.fonts/fontinfo/
---
## FontInfo class

Especifica información sobre una fuente utilizada en el documento.

```csharp
public class FontInfo
```

## Propiedades

| Nombre | Descripción |
| --- | --- |
| [AltName](../../aspose.words.fonts/fontinfo/altname/) { get; set; } | Obtiene o establece el nombre alternativo de la fuente. |
| [Charset](../../aspose.words.fonts/fontinfo/charset/) { get; set; } | Obtiene o establece el juego de caracteres para la fuente. |
| [Family](../../aspose.words.fonts/fontinfo/family/) { get; set; } | Obtiene o establece la familia de fuentes a la que pertenece esta fuente. |
| [IsTrueType](../../aspose.words.fonts/fontinfo/istruetype/) { get; set; } | Indica que esta fuente es una fuente TrueType u OpenType en lugar de una fuente rasterizada o vectorial. El valor predeterminado es verdadero. |
| [Name](../../aspose.words.fonts/fontinfo/name/) { get; } | Obtiene el nombre de la fuente. |
| [Panose](../../aspose.words.fonts/fontinfo/panose/) { get; set; } | Obtiene o establece el número de clasificación del tipo de letra PANOSE. |
| [Pitch](../../aspose.words.fonts/fontinfo/pitch/) { get; set; } | El paso indica si la fuente es de paso fijo, espaciada proporcionalmente o se basa en una configuración predeterminada. |

## Métodos

| Nombre | Descripción |
| --- | --- |
| [GetEmbeddedFont](../../aspose.words.fonts/fontinfo/getembeddedfont/)(EmbeddedFontFormat, EmbeddedFontStyle) | Obtiene un archivo de fuente incrustado específico. |
| [GetEmbeddedFontAsOpenType](../../aspose.words.fonts/fontinfo/getembeddedfontasopentype/)(EmbeddedFontStyle) | Obtiene un archivo de fuente incrustado en formato OpenType. Las fuentes en formato OpenType incrustado se convierten a OpenType. |

### Observaciones

No crea instancias de esta clase directamente. Usa el[`FontInfos`](../../aspose.words/documentbase/fontinfos/) propiedad para acceder a la colección de fuentes definidas en un documento.

### Ejemplos

Muestra cómo imprimir los detalles de qué fuentes están presentes en un documento.

```csharp
Document doc = new Document(MyDir + "Embedded font.docx");

FontInfoCollection allFonts = doc.FontInfos;
// Imprime todas las fuentes usadas y no usadas en el documento.
for (int i = 0; i < allFonts.Count; i++)
{
    Console.WriteLine($"Font index #{i}");
    Console.WriteLine($"\tName: {allFonts[i].Name}");
    Console.WriteLine($"\tIs {(allFonts[i].IsTrueType ? "" : "not ")}a trueType font");
}
```

### Ver también

* espacio de nombres [Aspose.Words.Fonts](../../aspose.words.fonts/)
* asamblea [Aspose.Words](../../)


