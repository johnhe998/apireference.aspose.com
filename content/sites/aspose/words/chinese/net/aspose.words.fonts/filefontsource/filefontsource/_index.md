---
title: FileFontSource.FileFontSource
second_title: Aspose.Words for .NET API 参考
description: FileFontSource 构造函数. 克托尔.
type: docs
weight: 10
url: /zh/net/aspose.words.fonts/filefontsource/filefontsource/
---
## FileFontSource(string) {#constructor}

克托尔.

```csharp
public FileFontSource(string filePath)
```

| 范围 | 类型 | 描述 |
| --- | --- | --- |
| filePath | String | 字体文件的路径。 |

### 例子

展示如何使用本地文件系统中的字体文件作为字体源。

```csharp
FileFontSource fileFontSource = new FileFontSource(MyDir + "Alte DIN 1451 Mittelschrift.ttf", 0);

Document doc = new Document();
doc.FontSettings = new FontSettings();
doc.FontSettings.SetFontsSources(new FontSourceBase[] {fileFontSource});

Assert.AreEqual(MyDir + "Alte DIN 1451 Mittelschrift.ttf", fileFontSource.FilePath);
Assert.AreEqual(FontSourceType.FontFile, fileFontSource.Type);
Assert.AreEqual(0, fileFontSource.Priority);
```

### 也可以看看

* class [FileFontSource](../)
* 命名空间 [Aspose.Words.Fonts](../../filefontsource/)
* 部件 [Aspose.Words](../../../)

---

## FileFontSource(string, int) {#constructor_1}

克托尔.

```csharp
public FileFontSource(string filePath, int priority)
```

| 范围 | 类型 | 描述 |
| --- | --- | --- |
| filePath | String | 字体文件的路径。 |
| priority | Int32 | 字体来源优先。见[`Priority`](../../fontsourcebase/priority/)属性描述以获取更多信息。 |

### 例子

展示如何使用本地文件系统中的字体文件作为字体源。

```csharp
FileFontSource fileFontSource = new FileFontSource(MyDir + "Alte DIN 1451 Mittelschrift.ttf", 0);

Document doc = new Document();
doc.FontSettings = new FontSettings();
doc.FontSettings.SetFontsSources(new FontSourceBase[] {fileFontSource});

Assert.AreEqual(MyDir + "Alte DIN 1451 Mittelschrift.ttf", fileFontSource.FilePath);
Assert.AreEqual(FontSourceType.FontFile, fileFontSource.Type);
Assert.AreEqual(0, fileFontSource.Priority);
```

### 也可以看看

* class [FileFontSource](../)
* 命名空间 [Aspose.Words.Fonts](../../filefontsource/)
* 部件 [Aspose.Words](../../../)

---

## FileFontSource(string, int, string) {#constructor_2}

克托尔.

```csharp
public FileFontSource(string filePath, int priority, string cacheKey)
```

| 范围 | 类型 | 描述 |
| --- | --- | --- |
| filePath | String | 字体文件的路径。 |
| priority | Int32 | 字体来源优先。见[`Priority`](../../fontsourcebase/priority/)属性描述以获取更多信息。 |
| cacheKey | String | 此源在缓存中的键。看[`CacheKey`](../cachekey/)属性描述以获取更多信息。 |

### 例子

显示如何加快字体缓存初始化过程。

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
/// 仅在需要时才加载字体数据，而不是将其存储在内存中
/// 对于“FontSettings”对象的整个生命周期。
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

### 也可以看看

* class [FileFontSource](../)
* 命名空间 [Aspose.Words.Fonts](../../filefontsource/)
* 部件 [Aspose.Words](../../../)


