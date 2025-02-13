---
title: MemoryFontSource.MemoryFontSource
second_title: Aspose.Words لمراجع .NET API
description: MemoryFontSource البناء. Ctor.
type: docs
weight: 10
url: /ar/net/aspose.words.fonts/memoryfontsource/memoryfontsource/
---
## MemoryFontSource(byte[]) {#constructor}

Ctor.

```csharp
public MemoryFontSource(byte[] fontData)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| fontData | Byte[] | بيانات الخط الثنائي. |

### أمثلة

يوضح كيفية استخدام مصفوفة بايت مع بيانات من ملف خط كمصدر خط.

```csharp
byte[] fontBytes = File.ReadAllBytes(MyDir + "Alte DIN 1451 Mittelschrift.ttf");
MemoryFontSource memoryFontSource = new MemoryFontSource(fontBytes, 0);

Document doc = new Document();
doc.FontSettings = new FontSettings();
doc.FontSettings.SetFontsSources(new FontSourceBase[] {memoryFontSource});

Assert.AreEqual(FontSourceType.MemoryFont, memoryFontSource.Type);
Assert.AreEqual(0, memoryFontSource.Priority);
```

### أنظر أيضا

* class [MemoryFontSource](../)
* مساحة الاسم [Aspose.Words.Fonts](../../memoryfontsource/)
* المجسم [Aspose.Words](../../../)

---

## MemoryFontSource(byte[], int) {#constructor_1}

Ctor.

```csharp
public MemoryFontSource(byte[] fontData, int priority)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| fontData | Byte[] | بيانات الخط الثنائي. |
| priority | Int32 | أولوية مصدر الخط. انظر[`Priority`](../../fontsourcebase/priority/) وصف الخاصية لمزيد من المعلومات. |

### أمثلة

يوضح كيفية استخدام مصفوفة بايت مع بيانات من ملف خط كمصدر خط.

```csharp
byte[] fontBytes = File.ReadAllBytes(MyDir + "Alte DIN 1451 Mittelschrift.ttf");
MemoryFontSource memoryFontSource = new MemoryFontSource(fontBytes, 0);

Document doc = new Document();
doc.FontSettings = new FontSettings();
doc.FontSettings.SetFontsSources(new FontSourceBase[] {memoryFontSource});

Assert.AreEqual(FontSourceType.MemoryFont, memoryFontSource.Type);
Assert.AreEqual(0, memoryFontSource.Priority);
```

### أنظر أيضا

* class [MemoryFontSource](../)
* مساحة الاسم [Aspose.Words.Fonts](../../memoryfontsource/)
* المجسم [Aspose.Words](../../../)

---

## MemoryFontSource(byte[], int, string) {#constructor_2}

Ctor.

```csharp
public MemoryFontSource(byte[] fontData, int priority, string cacheKey)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| fontData | Byte[] | بيانات الخط الثنائي. |
| priority | Int32 | أولوية مصدر الخط. انظر[`Priority`](../../fontsourcebase/priority/) وصف الخاصية لمزيد من المعلومات. |
| cacheKey | String | مفتاح هذا المصدر في ذاكرة التخزين المؤقت. نرى[`CacheKey`](../cachekey/) وصف الخاصية لمزيد من المعلومات. |

### أمثلة

يوضح كيفية تسريع عملية تهيئة ذاكرة التخزين المؤقت للخط.

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
/// قم بتحميل بيانات الخط عند الحاجة فقط بدلاً من تخزينها في الذاكرة
/// لكامل عمر الكائن "FontSettings".
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

### أنظر أيضا

* class [MemoryFontSource](../)
* مساحة الاسم [Aspose.Words.Fonts](../../memoryfontsource/)
* المجسم [Aspose.Words](../../../)


