---
title: MemoryFontSource.MemoryFontSource
second_title: Справочник по API Aspose.Words для .NET
description: MemoryFontSource строитель. Стор.
type: docs
weight: 10
url: /ru/net/aspose.words.fonts/memoryfontsource/memoryfontsource/
---
## MemoryFontSource(byte[]) {#constructor}

Стор.

```csharp
public MemoryFontSource(byte[] fontData)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| fontData | Byte[] | Данные двоичного шрифта. |

### Примеры

Показывает, как использовать массив байтов с данными из файла шрифта в качестве источника шрифта.

```csharp
byte[] fontBytes = File.ReadAllBytes(MyDir + "Alte DIN 1451 Mittelschrift.ttf");
MemoryFontSource memoryFontSource = new MemoryFontSource(fontBytes, 0);

Document doc = new Document();
doc.FontSettings = new FontSettings();
doc.FontSettings.SetFontsSources(new FontSourceBase[] {memoryFontSource});

Assert.AreEqual(FontSourceType.MemoryFont, memoryFontSource.Type);
Assert.AreEqual(0, memoryFontSource.Priority);
```

### Смотрите также

* class [MemoryFontSource](../)
* пространство имен [Aspose.Words.Fonts](../../memoryfontsource/)
* сборка [Aspose.Words](../../../)

---

## MemoryFontSource(byte[], int) {#constructor_1}

Стор.

```csharp
public MemoryFontSource(byte[] fontData, int priority)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| fontData | Byte[] | Данные двоичного шрифта. |
| priority | Int32 | Приоритет источника шрифта. См.[`Priority`](../../fontsourcebase/priority/) описание свойства для получения дополнительной информации. |

### Примеры

Показывает, как использовать массив байтов с данными из файла шрифта в качестве источника шрифта.

```csharp
byte[] fontBytes = File.ReadAllBytes(MyDir + "Alte DIN 1451 Mittelschrift.ttf");
MemoryFontSource memoryFontSource = new MemoryFontSource(fontBytes, 0);

Document doc = new Document();
doc.FontSettings = new FontSettings();
doc.FontSettings.SetFontsSources(new FontSourceBase[] {memoryFontSource});

Assert.AreEqual(FontSourceType.MemoryFont, memoryFontSource.Type);
Assert.AreEqual(0, memoryFontSource.Priority);
```

### Смотрите также

* class [MemoryFontSource](../)
* пространство имен [Aspose.Words.Fonts](../../memoryfontsource/)
* сборка [Aspose.Words](../../../)

---

## MemoryFontSource(byte[], int, string) {#constructor_2}

Стор.

```csharp
public MemoryFontSource(byte[] fontData, int priority, string cacheKey)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| fontData | Byte[] | Данные двоичного шрифта. |
| priority | Int32 | Приоритет источника шрифта. См.[`Priority`](../../fontsourcebase/priority/) описание свойства для получения дополнительной информации. |
| cacheKey | String | Ключ этого источника в кеше. Видеть[`CacheKey`](../cachekey/) описание свойства для получения дополнительной информации. |

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

* class [MemoryFontSource](../)
* пространство имен [Aspose.Words.Fonts](../../memoryfontsource/)
* сборка [Aspose.Words](../../../)


