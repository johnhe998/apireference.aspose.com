---
title: Enum FontSourceType
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Fonts.FontSourceType enumeración. Especifica el tipo de fuente de fuente.
type: docs
weight: 2810
url: /es/net/aspose.words.fonts/fontsourcetype/
---
## FontSourceType enumeration

Especifica el tipo de fuente de fuente.

```csharp
public enum FontSourceType
```

### Valores

| Nombre | Valor | Descripción |
| --- | --- | --- |
| FontFile | `0` | A[`FileFontSource`](../filefontsource/) objeto que representa un solo archivo de fuente. |
| FontsFolder | `1` | A[`FolderFontSource`](../folderfontsource/) objeto que representa carpeta con archivos de fuentes. |
| MemoryFont | `2` | A[`MemoryFontSource`](../memoryfontsource/) objeto que representa una sola fuente en la memoria. |
| SystemFonts | `3` | A[`SystemFontSource`](../systemfontsource/) objeto que representa todas las fuentes instaladas en el sistema. |
| FontStream | `4` | A[`StreamFontSource`](../streamfontsource/) objeto que representa un flujo con fuente data. |

### Ejemplos

Muestra cómo utilizar un archivo de fuente en el sistema de archivos local como fuente de fuente.

```csharp
FileFontSource fileFontSource = new FileFontSource(MyDir + "Alte DIN 1451 Mittelschrift.ttf", 0);

Document doc = new Document();
doc.FontSettings = new FontSettings();
doc.FontSettings.SetFontsSources(new FontSourceBase[] {fileFontSource});

Assert.AreEqual(MyDir + "Alte DIN 1451 Mittelschrift.ttf", fileFontSource.FilePath);
Assert.AreEqual(FontSourceType.FontFile, fileFontSource.Type);
Assert.AreEqual(0, fileFontSource.Priority);
```

### Ver también

* espacio de nombres [Aspose.Words.Fonts](../../aspose.words.fonts/)
* asamblea [Aspose.Words](../../)


