---
title: FontSettings.SaveSearchCache
second_title: Referencia de API de Aspose.Words para .NET
description: FontSettings método. Guarda la caché de búsqueda de fuentes en la secuencia.
type: docs
weight: 70
url: /es/net/aspose.words.fonts/fontsettings/savesearchcache/
---
## FontSettings.SaveSearchCache method

Guarda la caché de búsqueda de fuentes en la secuencia.

```csharp
public void SaveSearchCache(Stream outputStream)
```

| Parámetro | Escribe | Descripción |
| --- | --- | --- |
| outputStream | Stream | Salida de corriente. |

### Observaciones

Ver[`SetFontsSources`](../setfontssources/) descripción del método para más info.

### Ejemplos

Muestra cómo acelerar el proceso de inicialización de caché de fuentes.

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
/// Cargue los datos de la fuente solo cuando sea necesario en lugar de almacenarlos en la memoria
/// durante toda la vida útil del objeto "FontSettings".
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

### Ver también

* class [FontSettings](../)
* espacio de nombres [Aspose.Words.Fonts](../../fontsettings/)
* asamblea [Aspose.Words](../../../)


