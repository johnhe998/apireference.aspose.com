---
title: MemoryFontSource.MemoryFontSource
second_title: Aspose.Words per .NET API Reference
description: MemoryFontSource costruttore. Tor.
type: docs
weight: 10
url: /it/net/aspose.words.fonts/memoryfontsource/memoryfontsource/
---
## MemoryFontSource(byte[]) {#constructor}

Tor.

```csharp
public MemoryFontSource(byte[] fontData)
```

| Parametro | Tipo | Descrizione |
| --- | --- | --- |
| fontData | Byte[] | Dati di carattere binario. |

### Esempi

Mostra come utilizzare una matrice di byte con i dati di un file di font come origine di font.

```csharp
byte[] fontBytes = File.ReadAllBytes(MyDir + "Alte DIN 1451 Mittelschrift.ttf");
MemoryFontSource memoryFontSource = new MemoryFontSource(fontBytes, 0);

Document doc = new Document();
doc.FontSettings = new FontSettings();
doc.FontSettings.SetFontsSources(new FontSourceBase[] {memoryFontSource});

Assert.AreEqual(FontSourceType.MemoryFont, memoryFontSource.Type);
Assert.AreEqual(0, memoryFontSource.Priority);
```

### Guarda anche

* class [MemoryFontSource](../)
* spazio dei nomi [Aspose.Words.Fonts](../../memoryfontsource/)
* assemblea [Aspose.Words](../../../)

---

## MemoryFontSource(byte[], int) {#constructor_1}

Tor.

```csharp
public MemoryFontSource(byte[] fontData, int priority)
```

| Parametro | Tipo | Descrizione |
| --- | --- | --- |
| fontData | Byte[] | Dati di carattere binario. |
| priority | Int32 | Priorità origine carattere. Vedi il[`Priority`](../../fontsourcebase/priority/) descrizione della struttura per ulteriori informazioni. |

### Esempi

Mostra come utilizzare una matrice di byte con i dati di un file di font come origine di font.

```csharp
byte[] fontBytes = File.ReadAllBytes(MyDir + "Alte DIN 1451 Mittelschrift.ttf");
MemoryFontSource memoryFontSource = new MemoryFontSource(fontBytes, 0);

Document doc = new Document();
doc.FontSettings = new FontSettings();
doc.FontSettings.SetFontsSources(new FontSourceBase[] {memoryFontSource});

Assert.AreEqual(FontSourceType.MemoryFont, memoryFontSource.Type);
Assert.AreEqual(0, memoryFontSource.Priority);
```

### Guarda anche

* class [MemoryFontSource](../)
* spazio dei nomi [Aspose.Words.Fonts](../../memoryfontsource/)
* assemblea [Aspose.Words](../../../)

---

## MemoryFontSource(byte[], int, string) {#constructor_2}

Tor.

```csharp
public MemoryFontSource(byte[] fontData, int priority, string cacheKey)
```

| Parametro | Tipo | Descrizione |
| --- | --- | --- |
| fontData | Byte[] | Dati di carattere binario. |
| priority | Int32 | Priorità origine carattere. Vedi il[`Priority`](../../fontsourcebase/priority/) descrizione della struttura per ulteriori informazioni. |
| cacheKey | String | La chiave di questa fonte nella cache. Vedere[`CacheKey`](../cachekey/) descrizione della struttura per ulteriori informazioni. |

### Esempi

Mostra come accelerare il processo di inizializzazione della cache dei caratteri.

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
/// Carica i dati del font solo quando richiesto invece di salvarli in memoria
/// per l'intera durata dell'oggetto "FontSettings".
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

### Guarda anche

* class [MemoryFontSource](../)
* spazio dei nomi [Aspose.Words.Fonts](../../memoryfontsource/)
* assemblea [Aspose.Words](../../../)


