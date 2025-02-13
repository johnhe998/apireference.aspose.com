---
title: FolderFontSource.FolderPath
second_title: Referencia de API de Aspose.Words para .NET
description: FolderFontSource propiedad. Ruta a la carpeta.
type: docs
weight: 20
url: /es/net/aspose.words.fonts/folderfontsource/folderpath/
---
## FolderFontSource.FolderPath property

Ruta a la carpeta.

```csharp
public string FolderPath { get; }
```

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

* class [FolderFontSource](../)
* espacio de nombres [Aspose.Words.Fonts](../../folderfontsource/)
* asamblea [Aspose.Words](../../../)


