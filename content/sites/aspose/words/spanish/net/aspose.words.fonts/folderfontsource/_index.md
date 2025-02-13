---
title: Class FolderFontSource
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Fonts.FolderFontSource clase. Representa la carpeta que contiene archivos de fuentes TrueType.
type: docs
weight: 2700
url: /es/net/aspose.words.fonts/folderfontsource/
---
## FolderFontSource class

Representa la carpeta que contiene archivos de fuentes TrueType.

```csharp
public class FolderFontSource : FontSourceBase
```

## Constructores

| Nombre | Descripción |
| --- | --- |
| [FolderFontSource](folderfontsource/#constructor)(string, bool) | Director |
| [FolderFontSource](folderfontsource/#constructor_1)(string, bool, int) | Director |

## Propiedades

| Nombre | Descripción |
| --- | --- |
| [FolderPath](../../aspose.words.fonts/folderfontsource/folderpath/) { get; } | Ruta a la carpeta. |
| [Priority](../../aspose.words.fonts/fontsourcebase/priority/) { get; } | Devuelve la prioridad de origen de la fuente. |
| [ScanSubfolders](../../aspose.words.fonts/folderfontsource/scansubfolders/) { get; } | Determina si escanear o no las subcarpetas. |
| override [Type](../../aspose.words.fonts/folderfontsource/type/) { get; } | Devuelve el tipo de fuente fuente. |
| [WarningCallback](../../aspose.words.fonts/fontsourcebase/warningcallback/) { get; set; } | Llamado durante el procesamiento del origen de la fuente cuando se detecta un problema que podría resultar en la pérdida de fidelidad del formato. |

## Métodos

| Nombre | Descripción |
| --- | --- |
| [GetAvailableFonts](../../aspose.words.fonts/fontsourcebase/getavailablefonts/)() | Devuelve la lista de fuentes disponibles a través de esta fuente. |

### Ejemplos

Muestra cómo utilizar una carpeta del sistema local que contiene fuentes como fuente de fuentes.

```csharp
// Cree una fuente de fuentes a partir de una carpeta que contenga archivos de fuentes.
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, false, 1);

Document doc = new Document();
doc.FontSettings = new FontSettings();
doc.FontSettings.SetFontsSources(new FontSourceBase[] {folderFontSource});

Assert.AreEqual(FontsDir, folderFontSource.FolderPath);
Assert.AreEqual(false, folderFontSource.ScanSubfolders);
Assert.AreEqual(FontSourceType.FontsFolder, folderFontSource.Type);
Assert.AreEqual(1, folderFontSource.Priority);
```

### Ver también

* class [FontSourceBase](../fontsourcebase/)
* espacio de nombres [Aspose.Words.Fonts](../../aspose.words.fonts/)
* asamblea [Aspose.Words](../../)


