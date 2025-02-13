---
title: FontSettings.SaveSearchCache
second_title: Aspose.Words لمراجع .NET API
description: FontSettings طريقة. يحفظ ذاكرة التخزين المؤقت للبحث عن الخط في الدفق.
type: docs
weight: 70
url: /ar/net/aspose.words.fonts/fontsettings/savesearchcache/
---
## FontSettings.SaveSearchCache method

يحفظ ذاكرة التخزين المؤقت للبحث عن الخط في الدفق.

```csharp
public void SaveSearchCache(Stream outputStream)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| outputStream | Stream | تيار الإخراج. |

### ملاحظات

نرى[`SetFontsSources`](../setfontssources/) وصف الطريقة لمزيد من المعلومات.

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

* class [FontSettings](../)
* مساحة الاسم [Aspose.Words.Fonts](../../fontsettings/)
* المجسم [Aspose.Words](../../../)


