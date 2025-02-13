---
title: Class FontSourceBase
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Fonts.FontSourceBase sınıf. Bu kullanıcının çeşitli yazı tipi kaynaklarını belirlemesine izin veren sınıflar için soyut bir temel sınıftır.
type: docs
weight: 2800
url: /tr/net/aspose.words.fonts/fontsourcebase/
---
## FontSourceBase class

Bu, kullanıcının çeşitli yazı tipi kaynaklarını belirlemesine izin veren sınıflar için soyut bir temel sınıftır.

```csharp
public abstract class FontSourceBase
```

## Özellikleri

| İsim | Tanım |
| --- | --- |
| [Priority](../../aspose.words.fonts/fontsourcebase/priority/) { get; } | Yazı tipi kaynağı önceliğini döndürür. |
| abstract [Type](../../aspose.words.fonts/fontsourcebase/type/) { get; } | Yazı tipi kaynağının türünü döndürür. |
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

* ad alanı [Aspose.Words.Fonts](../../aspose.words.fonts/)
* toplantı [Aspose.Words](../../)


