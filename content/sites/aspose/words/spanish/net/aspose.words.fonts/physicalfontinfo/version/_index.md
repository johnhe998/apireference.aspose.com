---
title: PhysicalFontInfo.Version
second_title: Referencia de API de Aspose.Words para .NET
description: PhysicalFontInfo propiedad. Cadena de versión de la fuente.
type: docs
weight: 40
url: /es/net/aspose.words.fonts/physicalfontinfo/version/
---
## PhysicalFontInfo.Version property

Cadena de versión de la fuente.

```csharp
public string Version { get; }
```

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

* class [PhysicalFontInfo](../)
* espacio de nombres [Aspose.Words.Fonts](../../physicalfontinfo/)
* asamblea [Aspose.Words](../../../)


