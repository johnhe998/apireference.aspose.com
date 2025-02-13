---
title: Class FileFontSource
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Fonts.FileFontSource sınıf. Dosya sisteminde depolanan tek TrueType yazı tipi dosyasını temsil eder.
type: docs
weight: 2690
url: /tr/net/aspose.words.fonts/filefontsource/
---
## FileFontSource class

Dosya sisteminde depolanan tek TrueType yazı tipi dosyasını temsil eder.

```csharp
public class FileFontSource : FontSourceBase
```

## yapıcılar

| İsim | Tanım |
| --- | --- |
| [FileFontSource](filefontsource/#constructor)(string) | Ctor. |
| [FileFontSource](filefontsource/#constructor_1)(string, int) | Ctor. |
| [FileFontSource](filefontsource/#constructor_2)(string, int, string) | Ctor. |

## Özellikleri

| İsim | Tanım |
| --- | --- |
| [CacheKey](../../aspose.words.fonts/filefontsource/cachekey/) { get; } | Önbellekteki bu kaynağın anahtarı. |
| [FilePath](../../aspose.words.fonts/filefontsource/filepath/) { get; } | Yazı tipi dosyasının yolu. |
| [Priority](../../aspose.words.fonts/fontsourcebase/priority/) { get; } | Yazı tipi kaynağı önceliğini döndürür. |
| override [Type](../../aspose.words.fonts/filefontsource/type/) { get; } | Yazı tipi kaynağının türünü döndürür. |
| [WarningCallback](../../aspose.words.fonts/fontsourcebase/warningcallback/) { get; set; } | Biçimlendirme aslına uygunluk kaybına neden olabilecek bir sorun algılandığında yazı tipi kaynağının işlenmesi sırasında çağrılır. |

## yöntemler

| İsim | Tanım |
| --- | --- |
| [GetAvailableFonts](../../aspose.words.fonts/fontsourcebase/getavailablefonts/)() | Bu kaynak aracılığıyla kullanılabilen yazı tiplerinin listesini döndürür. |

### Örnekler

Yerel dosya sistemindeki bir yazı tipi dosyasının yazı tipi kaynağı olarak nasıl kullanılacağını gösterir.

```csharp
FileFontSource fileFontSource = new FileFontSource(MyDir + "Alte DIN 1451 Mittelschrift.ttf", 0);

Document doc = new Document();
doc.FontSettings = new FontSettings();
doc.FontSettings.SetFontsSources(new FontSourceBase[] {fileFontSource});

Assert.AreEqual(MyDir + "Alte DIN 1451 Mittelschrift.ttf", fileFontSource.FilePath);
Assert.AreEqual(FontSourceType.FontFile, fileFontSource.Type);
Assert.AreEqual(0, fileFontSource.Priority);
```

### Ayrıca bakınız

* class [FontSourceBase](../fontsourcebase/)
* ad alanı [Aspose.Words.Fonts](../../aspose.words.fonts/)
* toplantı [Aspose.Words](../../)


