---
title: Class FontSourceBase
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Fonts.FontSourceBase clase. Esta es una clase base abstracta para las clases que permiten al usuario especificar varias fuentes de fuentes.
type: docs
weight: 2800
url: /es/net/aspose.words.fonts/fontsourcebase/
---
## FontSourceBase class

Esta es una clase base abstracta para las clases que permiten al usuario especificar varias fuentes de fuentes.

```csharp
public abstract class FontSourceBase
```

## Propiedades

| Nombre | Descripción |
| --- | --- |
| [Priority](../../aspose.words.fonts/fontsourcebase/priority/) { get; } | Devuelve la prioridad de origen de la fuente. |
| abstract [Type](../../aspose.words.fonts/fontsourcebase/type/) { get; } | Devuelve el tipo de fuente fuente. |
| [WarningCallback](../../aspose.words.fonts/fontsourcebase/warningcallback/) { get; set; } | Llamado durante el procesamiento del origen de la fuente cuando se detecta un problema que podría resultar en la pérdida de fidelidad del formato. |

## Métodos

| Nombre | Descripción |
| --- | --- |
| [GetAvailableFonts](../../aspose.words.fonts/fontsourcebase/getavailablefonts/)() | Devuelve la lista de fuentes disponibles a través de esta fuente. |

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


