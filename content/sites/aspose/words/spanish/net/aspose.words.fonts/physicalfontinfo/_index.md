---
title: Class PhysicalFontInfo
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Fonts.PhysicalFontInfo clase. Especifica información sobre la fuente física disponible para el motor de fuente Aspose.Words.
type: docs
weight: 2850
url: /es/net/aspose.words.fonts/physicalfontinfo/
---
## PhysicalFontInfo class

Especifica información sobre la fuente física disponible para el motor de fuente Aspose.Words.

```csharp
public class PhysicalFontInfo
```

## Propiedades

| Nombre | Descripción |
| --- | --- |
| [FilePath](../../aspose.words.fonts/physicalfontinfo/filepath/) { get; } | Ruta al archivo de fuente si lo hay. |
| [FontFamilyName](../../aspose.words.fonts/physicalfontinfo/fontfamilyname/) { get; } | Nombre de familia de la fuente. |
| [FullFontName](../../aspose.words.fonts/physicalfontinfo/fullfontname/) { get; } | Nombre completo de la fuente. |
| [Version](../../aspose.words.fonts/physicalfontinfo/version/) { get; } | Cadena de versión de la fuente. |

### Ejemplos

Muestra cómo enumerar las fuentes disponibles.

```csharp
// Configure Aspose.Words para obtener fuentes de una carpeta personalizada y luego imprima todas las fuentes disponibles.
FontSourceBase[] folderFontSource = { new FolderFontSource(FontsDir, true) };

foreach (PhysicalFontInfo fontInfo in folderFontSource[0].GetAvailableFonts())
{
    Console.WriteLine("FontFamilyName : {0}", fontInfo.FontFamilyName);
    Console.WriteLine("FullFontName  : {0}", fontInfo.FullFontName);
    Console.WriteLine("Version  : {0}", fontInfo.Version);
    Console.WriteLine("FilePath : {0}\n", fontInfo.FilePath);
}
```

### Ver también

* espacio de nombres [Aspose.Words.Fonts](../../aspose.words.fonts/)
* asamblea [Aspose.Words](../../)


