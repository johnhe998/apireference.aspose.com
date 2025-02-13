---
title: FontSettings.GetFontsSources
second_title: Aspose.Words for .NET API Referansı
description: FontSettings yöntem. Aspose.Wordsün TrueType yazı tiplerini aradığı kaynakların listesini içeren dizinin bir kopyasını alır.
type: docs
weight: 50
url: /tr/net/aspose.words.fonts/fontsettings/getfontssources/
---
## FontSettings.GetFontsSources method

Aspose.Words'ün TrueType yazı tiplerini aradığı kaynakların listesini içeren dizinin bir kopyasını alır.

```csharp
public FontSourceBase[] GetFontsSources()
```

### Geri dönüş değeri

Geçerli yazı tipi kaynaklarının bir kopyası.

### Notlar

Döndürülen değer, Aspose.Words'ün kullandığı verilerin bir kopyasıdır. Döndürülen dizideki girişleri değiştirirseniz, belge oluşturma üzerinde hiçbir etkisi olmaz. Yeni yazı tipi source belirtmek için şunu kullanın:[`SetFontsSources`](../setfontssources/) yöntem.

### Örnekler

Mevcut yazı tipi kaynaklarımıza nasıl yazı tipi kaynağı ekleneceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Name = "Arial";
builder.Writeln("Hello world!");
builder.Font.Name = "Amethysta";
builder.Writeln("The quick brown fox jumps over the lazy dog.");
builder.Font.Name = "Junction Light";
builder.Writeln("The quick brown fox jumps over the lazy dog.");

FontSourceBase[] originalFontSources = FontSettings.DefaultInstance.GetFontsSources();

Assert.AreEqual(1, originalFontSources.Length);

Assert.True(originalFontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Arial"));

// Varsayılan yazı tipi kaynağında, belgemizde kullandığımız yazı tiplerinden ikisi eksik.
// Bu belgeyi kaydettiğimizde, Aspose.Words, erişilemeyen yazı tipleriyle formatlanmış tüm metinlere yedek yazı tipleri uygulayacaktır.
Assert.False(originalFontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Amethysta"));
Assert.False(originalFontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Junction Light"));

// Fontları içeren bir klasörden bir font kaynağı oluşturun.
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, true);

// Özel yazı tiplerimizin yanı sıra orijinal yazı tipi kaynaklarını içeren yeni bir yazı tipi kaynakları dizisi uygulayın.
FontSourceBase[] updatedFontSources = {originalFontSources[0], folderFontSource};
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);

// Belgeyi PDF'ye dönüştürmeden önce Aspose.Words'ün gerekli tüm yazı tiplerine erişimi olduğunu doğrulayın.
updatedFontSources = FontSettings.DefaultInstance.GetFontsSources();

Assert.True(updatedFontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Arial"));
Assert.True(updatedFontSources[1].GetAvailableFonts().Any(f => f.FullFontName == "Amethysta"));
Assert.True(updatedFontSources[1].GetAvailableFonts().Any(f => f.FullFontName == "Junction Light"));

doc.Save(ArtifactsDir + "FontSettings.AddFontSource.pdf");

// Orijinal yazı tipi kaynaklarını geri yükleyin.
FontSettings.DefaultInstance.SetFontsSources(originalFontSources);
```

### Ayrıca bakınız

* class [FontSourceBase](../../fontsourcebase/)
* class [FontSettings](../)
* ad alanı [Aspose.Words.Fonts](../../fontsettings/)
* toplantı [Aspose.Words](../../../)


