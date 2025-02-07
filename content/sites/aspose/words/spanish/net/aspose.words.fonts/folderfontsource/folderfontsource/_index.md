---
title: FolderFontSource.FolderFontSource
second_title: Referencia de API de Aspose.Words para .NET
description: FolderFontSource constructor. Director
type: docs
weight: 10
url: /es/net/aspose.words.fonts/folderfontsource/folderfontsource/
---
## FolderFontSource(string, bool) {#constructor}

Director

```csharp
public FolderFontSource(string folderPath, bool scanSubfolders)
```

| Parámetro | Escribe | Descripción |
| --- | --- | --- |
| folderPath | String | Ruta a la carpeta. |
| scanSubfolders | Boolean | Determina si se escanearán o no las subcarpetas. |

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

---

## FolderFontSource(string, bool, int) {#constructor_1}

Director

```csharp
public FolderFontSource(string folderPath, bool scanSubfolders, int priority)
```

| Parámetro | Escribe | Descripción |
| --- | --- | --- |
| folderPath | String | Ruta a la carpeta. |
| scanSubfolders | Boolean | Determina si se escanearán o no las subcarpetas. |
| priority | Int32 | Prioridad de fuente de fuente. Ver el[`Priority`](../../fontsourcebase/priority/) descripción de la propiedad para más información. |

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


