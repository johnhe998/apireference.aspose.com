---
title: Class MemoryFontSource
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Fonts.MemoryFontSource sınıf. Bellekte depolanan tek TrueType yazı tipi dosyasını temsil eder.
type: docs
weight: 2840
url: /tr/net/aspose.words.fonts/memoryfontsource/
---
## MemoryFontSource class

Bellekte depolanan tek TrueType yazı tipi dosyasını temsil eder.

```csharp
public class MemoryFontSource : FontSourceBase
```

## yapıcılar

| İsim | Tanım |
| --- | --- |
| [MemoryFontSource](memoryfontsource/#constructor)(byte[]) | Ctor. |
| [MemoryFontSource](memoryfontsource/#constructor_1)(byte[], int) | Ctor. |
| [MemoryFontSource](memoryfontsource/#constructor_2)(byte[], int, string) | Ctor. |

## Özellikleri

| İsim | Tanım |
| --- | --- |
| [CacheKey](../../aspose.words.fonts/memoryfontsource/cachekey/) { get; } | Önbellekteki bu kaynağın anahtarı. |
| [FontData](../../aspose.words.fonts/memoryfontsource/fontdata/) { get; } | İkili yazı tipi verileri. |
| [Priority](../../aspose.words.fonts/fontsourcebase/priority/) { get; } | Yazı tipi kaynağı önceliğini döndürür. |
| override [Type](../../aspose.words.fonts/memoryfontsource/type/) { get; } | Yazı tipi kaynağının türünü döndürür. |
| [WarningCallback](../../aspose.words.fonts/fontsourcebase/warningcallback/) { get; set; } | Biçimlendirme aslına uygunluk kaybına neden olabilecek bir sorun algılandığında yazı tipi kaynağının işlenmesi sırasında çağrılır. |

## yöntemler

| İsim | Tanım |
| --- | --- |
| [GetAvailableFonts](../../aspose.words.fonts/fontsourcebase/getavailablefonts/)() | Bu kaynak aracılığıyla kullanılabilen yazı tiplerinin listesini döndürür. |

### Örnekler

Yazı tipi kaynağı olarak bir yazı tipi dosyasındaki verilerle bir bayt dizisinin nasıl kullanılacağını gösterir.

```csharp
byte[] fontBytes = File.ReadAllBytes(MyDir + "Alte DIN 1451 Mittelschrift.ttf");
MemoryFontSource memoryFontSource = new MemoryFontSource(fontBytes, 0);

Document doc = new Document();
doc.FontSettings = new FontSettings();
doc.FontSettings.SetFontsSources(new FontSourceBase[] {memoryFontSource});

Assert.AreEqual(FontSourceType.MemoryFont, memoryFontSource.Type);
Assert.AreEqual(0, memoryFontSource.Priority);
```

### Ayrıca bakınız

* class [FontSourceBase](../fontsourcebase/)
* ad alanı [Aspose.Words.Fonts](../../aspose.words.fonts/)
* toplantı [Aspose.Words](../../)


