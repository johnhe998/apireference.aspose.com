---
title: FontInfo.IsTrueType
second_title: Referencia de API de Aspose.Words para .NET
description: FontInfo propiedad. Indica que esta fuente es una fuente TrueType u OpenType en lugar de una fuente rasterizada o vectorial. El valor predeterminado es verdadero.
type: docs
weight: 40
url: /es/net/aspose.words.fonts/fontinfo/istruetype/
---
## FontInfo.IsTrueType property

Indica que esta fuente es una fuente TrueType u OpenType en lugar de una fuente rasterizada o vectorial. El valor predeterminado es verdadero.

```csharp
public bool IsTrueType { get; set; }
```

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

* class [FontInfo](../)
* espacio de nombres [Aspose.Words.Fonts](../../fontinfo/)
* asamblea [Aspose.Words](../../../)


