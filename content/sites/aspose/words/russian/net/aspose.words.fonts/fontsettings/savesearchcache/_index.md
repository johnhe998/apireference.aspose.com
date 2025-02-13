---
title: FontSettings.SaveSearchCache
second_title: Справочник по API Aspose.Words для .NET
description: FontSettings метод. Сохраняет кеш поиска шрифтов в поток.
type: docs
weight: 70
url: /ru/net/aspose.words.fonts/fontsettings/savesearchcache/
---
## FontSettings.SaveSearchCache method

Сохраняет кеш поиска шрифтов в поток.

```csharp
public void SaveSearchCache(Stream outputStream)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| outputStream | Stream | Выходной поток. |

### Примечания

Видеть[`SetFontsSources`](../setfontssources/) описание метода для получения дополнительной информации.

### Примеры

Показывает, как ускорить процесс инициализации кэша шрифтов.

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
/// Загружаем данные шрифта только при необходимости, а не сохраняем их в памяти
/// на все время жизни объекта FontSettings.
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

### Смотрите также

* class [FontSettings](../)
* пространство имен [Aspose.Words.Fonts](../../fontsettings/)
* сборка [Aspose.Words](../../../)


