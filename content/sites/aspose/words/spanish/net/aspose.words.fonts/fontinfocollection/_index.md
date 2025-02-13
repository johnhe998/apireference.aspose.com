---
title: Class FontInfoCollection
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Fonts.FontInfoCollection clase. Representa una colección de fuentes utilizadas en un documento.
type: docs
weight: 2750
url: /es/net/aspose.words.fonts/fontinfocollection/
---
## FontInfoCollection class

Representa una colección de fuentes utilizadas en un documento.

```csharp
public class FontInfoCollection : IEnumerable<FontInfo>
```

## Propiedades

| Nombre | Descripción |
| --- | --- |
| [Count](../../aspose.words.fonts/fontinfocollection/count/) { get; } | Obtiene el número de elementos que contiene la colección. |
| [EmbedSystemFonts](../../aspose.words.fonts/fontinfocollection/embedsystemfonts/) { get; set; } | Especifica si se incrustan o no las fuentes del sistema en el documento. El valor predeterminado para esta propiedad es **falso**. |
| [EmbedTrueTypeFonts](../../aspose.words.fonts/fontinfocollection/embedtruetypefonts/) { get; set; } | Especifica si se incrustan o no fuentes TrueType en un documento cuando se guarda. El valor predeterminado para esta propiedad es **falso** . |
| [Item](../../aspose.words.fonts/fontinfocollection/item/) { get; } | Obtiene una fuente con el nombre especificado. (2 indexers) |
| [SaveSubsetFonts](../../aspose.words.fonts/fontinfocollection/savesubsetfonts/) { get; set; } | Especifica si guardar o no un subconjunto de las fuentes TrueType incrustadas con el documento. El valor predeterminado para esta propiedad es **falso**. |

## Métodos

| Nombre | Descripción |
| --- | --- |
| [Contains](../../aspose.words.fonts/fontinfocollection/contains/)(string) | Determina si la colección contiene una fuente con el nombre dado. |
| [GetEnumerator](../../aspose.words.fonts/fontinfocollection/getenumerator/)() | Devuelve un objeto enumerador que se puede usar para iterar sobre todos los elementos de la colección. |

### Observaciones

Los artículos son[`FontInfo`](../fontinfo/) objetos.

No crea instancias de esta clase directamente. Usa el[`FontInfos`](../../aspose.words/documentbase/fontinfos/) propiedad para acceder a la colección de fuentes definidas en el documento.

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

Muestra cómo guardar un documento con fuentes TrueType incrustadas.

```csharp
Document doc = new Document(MyDir + "Document.docx");

FontInfoCollection fontInfos = doc.FontInfos;
fontInfos.EmbedTrueTypeFonts = embedAllFonts;
fontInfos.EmbedSystemFonts = embedAllFonts;
fontInfos.SaveSubsetFonts = embedAllFonts;

doc.Save(ArtifactsDir + "Font.FontInfoCollection.docx");

if (embedAllFonts)
    Assert.That(25000, Is.LessThan(new FileInfo(ArtifactsDir + "Font.FontInfoCollection.docx").Length));
else
    Assert.That(15000, Is.AtLeast(new FileInfo(ArtifactsDir + "Font.FontInfoCollection.docx").Length));
```

### Ver también

* class [FontInfo](../fontinfo/)
* espacio de nombres [Aspose.Words.Fonts](../../aspose.words.fonts/)
* asamblea [Aspose.Words](../../)


