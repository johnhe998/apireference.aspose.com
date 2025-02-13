---
title: FolderFontSource.FolderFontSource
second_title: Aspose.Words för .NET API Referens
description: FolderFontSource byggare. Ctor.
type: docs
weight: 10
url: /sv/net/aspose.words.fonts/folderfontsource/folderfontsource/
---
## FolderFontSource(string, bool) {#constructor}

Ctor.

```csharp
public FolderFontSource(string folderPath, bool scanSubfolders)
```

| Parameter | Typ | Beskrivning |
| --- | --- | --- |
| folderPath | String | Sökväg till mapp. |
| scanSubfolders | Boolean | Bestämmer om undermappar ska skannas eller inte. |

### Exempel

Visar hur man använder en lokal systemmapp som innehåller teckensnitt som teckensnittskälla.

```csharp
// Skapa en teckensnittskälla från en mapp som innehåller teckensnittsfiler.
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, false, 1);

Document doc = new Document();
doc.FontSettings = new FontSettings();
doc.FontSettings.SetFontsSources(new FontSourceBase[] {folderFontSource});

Assert.AreEqual(FontsDir, folderFontSource.FolderPath);
Assert.AreEqual(false, folderFontSource.ScanSubfolders);
Assert.AreEqual(FontSourceType.FontsFolder, folderFontSource.Type);
Assert.AreEqual(1, folderFontSource.Priority);
```

### Se även

* class [FolderFontSource](../)
* namnutrymme [Aspose.Words.Fonts](../../folderfontsource/)
* hopsättning [Aspose.Words](../../../)

---

## FolderFontSource(string, bool, int) {#constructor_1}

Ctor.

```csharp
public FolderFontSource(string folderPath, bool scanSubfolders, int priority)
```

| Parameter | Typ | Beskrivning |
| --- | --- | --- |
| folderPath | String | Sökväg till mapp. |
| scanSubfolders | Boolean | Bestämmer om undermappar ska skannas eller inte. |
| priority | Int32 | Teckensnittskällas prioritet. Se den[`Priority`](../../fontsourcebase/priority/) fastighetsbeskrivning för mer information. |

### Exempel

Visar hur man använder en lokal systemmapp som innehåller teckensnitt som teckensnittskälla.

```csharp
// Skapa en teckensnittskälla från en mapp som innehåller teckensnittsfiler.
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, false, 1);

Document doc = new Document();
doc.FontSettings = new FontSettings();
doc.FontSettings.SetFontsSources(new FontSourceBase[] {folderFontSource});

Assert.AreEqual(FontsDir, folderFontSource.FolderPath);
Assert.AreEqual(false, folderFontSource.ScanSubfolders);
Assert.AreEqual(FontSourceType.FontsFolder, folderFontSource.Type);
Assert.AreEqual(1, folderFontSource.Priority);
```

### Se även

* class [FolderFontSource](../)
* namnutrymme [Aspose.Words.Fonts](../../folderfontsource/)
* hopsättning [Aspose.Words](../../../)


