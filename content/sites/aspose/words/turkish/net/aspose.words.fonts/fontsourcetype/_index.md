---
title: Enum FontSourceType
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Fonts.FontSourceType Sıralama. Bir yazı tipi kaynağının türünü belirtir.
type: docs
weight: 2810
url: /tr/net/aspose.words.fonts/fontsourcetype/
---
## FontSourceType enumeration

Bir yazı tipi kaynağının türünü belirtir.

```csharp
public enum FontSourceType
```

### değerler

| İsim | Değer | Tanım |
| --- | --- | --- |
| FontFile | `0` | A[`FileFontSource`](../filefontsource/) tek yazı tipi dosyasını temsil eden nesne. |
| FontsFolder | `1` | A[`FolderFontSource`](../folderfontsource/) yazı tipi dosyaları içeren klasörü temsil eden nesne. |
| MemoryFont | `2` | A[`MemoryFontSource`](../memoryfontsource/) bellekte tek yazı tipini temsil eden nesne. |
| SystemFonts | `3` | A[`SystemFontSource`](../systemfontsource/) sistemde yüklü olan tüm yazı tiplerini temsil eden nesne. |
| FontStream | `4` | A[`StreamFontSource`](../streamfontsource/) yazı tipi verileriyle bir akışı temsil eden nesne. |

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


