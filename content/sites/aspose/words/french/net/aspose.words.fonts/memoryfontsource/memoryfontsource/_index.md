---
title: MemoryFontSource.MemoryFontSource
second_title: Référence de l'API Aspose.Words pour .NET
description: MemoryFontSource constructeur. Ctor.
type: docs
weight: 10
url: /fr/net/aspose.words.fonts/memoryfontsource/memoryfontsource/
---
## MemoryFontSource(byte[]) {#constructor}

Ctor.

```csharp
public MemoryFontSource(byte[] fontData)
```

| Paramètre | Taper | La description |
| --- | --- | --- |
| fontData | Byte[] | Données de police binaires. |

### Exemples

Montre comment utiliser un tableau d'octets avec les données d'un fichier de police comme source de police.

```csharp
byte[] fontBytes = File.ReadAllBytes(MyDir + "Alte DIN 1451 Mittelschrift.ttf");
MemoryFontSource memoryFontSource = new MemoryFontSource(fontBytes, 0);

Document doc = new Document();
doc.FontSettings = new FontSettings();
doc.FontSettings.SetFontsSources(new FontSourceBase[] {memoryFontSource});

Assert.AreEqual(FontSourceType.MemoryFont, memoryFontSource.Type);
Assert.AreEqual(0, memoryFontSource.Priority);
```

### Voir également

* class [MemoryFontSource](../)
* espace de noms [Aspose.Words.Fonts](../../memoryfontsource/)
* Assemblée [Aspose.Words](../../../)

---

## MemoryFontSource(byte[], int) {#constructor_1}

Ctor.

```csharp
public MemoryFontSource(byte[] fontData, int priority)
```

| Paramètre | Taper | La description |
| --- | --- | --- |
| fontData | Byte[] | Données de police binaires. |
| priority | Int32 | Priorité de source de police. Voir le[`Priority`](../../fontsourcebase/priority/) description de la propriété pour plus d'informations. |

### Exemples

Montre comment utiliser un tableau d'octets avec les données d'un fichier de police comme source de police.

```csharp
byte[] fontBytes = File.ReadAllBytes(MyDir + "Alte DIN 1451 Mittelschrift.ttf");
MemoryFontSource memoryFontSource = new MemoryFontSource(fontBytes, 0);

Document doc = new Document();
doc.FontSettings = new FontSettings();
doc.FontSettings.SetFontsSources(new FontSourceBase[] {memoryFontSource});

Assert.AreEqual(FontSourceType.MemoryFont, memoryFontSource.Type);
Assert.AreEqual(0, memoryFontSource.Priority);
```

### Voir également

* class [MemoryFontSource](../)
* espace de noms [Aspose.Words.Fonts](../../memoryfontsource/)
* Assemblée [Aspose.Words](../../../)

---

## MemoryFontSource(byte[], int, string) {#constructor_2}

Ctor.

```csharp
public MemoryFontSource(byte[] fontData, int priority, string cacheKey)
```

| Paramètre | Taper | La description |
| --- | --- | --- |
| fontData | Byte[] | Données de police binaires. |
| priority | Int32 | Priorité de source de police. Voir le[`Priority`](../../fontsourcebase/priority/) description de la propriété pour plus d'informations. |
| cacheKey | String | La clé de cette source dans le cache. Voir[`CacheKey`](../cachekey/) description de la propriété pour plus d'informations. |

### Exemples

Montre comment accélérer le processus d'initialisation du cache de polices.

```csharp
[Test]
public void LoadFontSearchCache()
{
    const string cacheKey1 = "Arvo";
    const string cacheKey2 = "Arvo-Bold";
    FontSettings parsedFonts = new FontSettings();
    FontSettings loadedCache = new FontSettings();

    parsedFonts.SetFontsSources(new FontSourceBase[]
    {
        new FileFontSource(FontsDir + "Arvo-Regular.ttf", 0, cacheKey1),
        new FileFontSource(FontsDir + "Arvo-Bold.ttf", 0, cacheKey2)
    });

    using (MemoryStream cacheStream = new MemoryStream())
    {
        parsedFonts.SaveSearchCache(cacheStream);
        loadedCache.SetFontsSources(new FontSourceBase[]
        {
            new SearchCacheStream(cacheKey1),                    
            new MemoryFontSource(File.ReadAllBytes(FontsDir + "Arvo-Bold.ttf"), 0, cacheKey2)
        }, cacheStream);
    }

    Assert.AreEqual(parsedFonts.GetFontsSources().Length, loadedCache.GetFontsSources().Length);
}

/// <summary>
/// Charger les données de police uniquement lorsque cela est nécessaire au lieu de les stocker dans la mémoire
/// pour toute la durée de vie de l'objet "FontSettings".
/// </summary>
private class SearchCacheStream : StreamFontSource
{
    public SearchCacheStream(string cacheKey):base(0, cacheKey)
    {
    }

    public override Stream OpenFontDataStream()
    {
        return File.OpenRead(FontsDir + "Arvo-Regular.ttf");
    }
}
```

### Voir également

* class [MemoryFontSource](../)
* espace de noms [Aspose.Words.Fonts](../../memoryfontsource/)
* Assemblée [Aspose.Words](../../../)


