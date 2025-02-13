---
title: Class FontInfo
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Fonts.FontInfo sınıf. Belgede kullanılan bir yazı tipi hakkındaki bilgileri belirtir.
type: docs
weight: 2740
url: /tr/net/aspose.words.fonts/fontinfo/
---
## FontInfo class

Belgede kullanılan bir yazı tipi hakkındaki bilgileri belirtir.

```csharp
public class FontInfo
```

## Özellikleri

| İsim | Tanım |
| --- | --- |
| [AltName](../../aspose.words.fonts/fontinfo/altname/) { get; set; } | Yazı tipinin alternatif adını alır veya ayarlar. |
| [Charset](../../aspose.words.fonts/fontinfo/charset/) { get; set; } | Yazı tipi için karakter kümesini alır veya ayarlar. |
| [Family](../../aspose.words.fonts/fontinfo/family/) { get; set; } | Bu yazı tipinin ait olduğu yazı tipi ailesini alır veya ayarlar. |
| [IsTrueType](../../aspose.words.fonts/fontinfo/istruetype/) { get; set; } | Bu yazı tipinin raster veya vektör yazı tipinin aksine bir TrueType veya OpenType yazı tipi olduğunu gösterir. Varsayılan değer true. |
| [Name](../../aspose.words.fonts/fontinfo/name/) { get; } | Yazı tipinin adını alır. |
| [Panose](../../aspose.words.fonts/fontinfo/panose/) { get; set; } | PANOSE yazı tipi sınıflandırma numarasını alır veya ayarlar. |
| [Pitch](../../aspose.words.fonts/fontinfo/pitch/) { get; set; } | Aralık, yazı tipinin sabit aralıklı mı, orantılı aralıklı mı yoksa varsayılan bir ayara mı dayalı olduğunu gösterir. |

## yöntemler

| İsim | Tanım |
| --- | --- |
| [GetEmbeddedFont](../../aspose.words.fonts/fontinfo/getembeddedfont/)(EmbeddedFontFormat, EmbeddedFontStyle) | Belirli bir gömülü yazı tipi dosyasını alır. |
| [GetEmbeddedFontAsOpenType](../../aspose.words.fonts/fontinfo/getembeddedfontasopentype/)(EmbeddedFontStyle) | OpenType biçiminde gömülü bir yazı tipi dosyası alır. Gömülü OpenType biçimindeki yazı tipleri OpenType. 'ye dönüştürülür |

### Notlar

Bu sınıfın örneklerini doğrudan oluşturmazsınız. [`FontInfos`](../../aspose.words/documentbase/fontinfos/) bir belgede tanımlanan yazı tiplerinin koleksiyonuna erişme özelliği.

### Örnekler

Bir belgede hangi yazı tiplerinin bulunduğunun ayrıntılarının nasıl yazdırılacağını gösterir.

```csharp
Document doc = new Document(MyDir + "Embedded font.docx");

FontInfoCollection allFonts = doc.FontInfos;
// Belgedeki tüm kullanılmış ve kullanılmayan yazı tiplerini yazdırın.
for (int i = 0; i < allFonts.Count; i++)
{
    Console.WriteLine($"Font index #{i}");
    Console.WriteLine($"\tName: {allFonts[i].Name}");
    Console.WriteLine($"\tIs {(allFonts[i].IsTrueType ? "" : "not ")}a trueType font");
}
```

### Ayrıca bakınız

* ad alanı [Aspose.Words.Fonts](../../aspose.words.fonts/)
* toplantı [Aspose.Words](../../)


