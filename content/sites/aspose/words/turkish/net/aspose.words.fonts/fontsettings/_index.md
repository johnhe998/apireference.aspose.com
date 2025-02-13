---
title: Class FontSettings
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Fonts.FontSettings sınıf. Bir belge için yazı tipi ayarlarını belirtir.
type: docs
weight: 2790
url: /tr/net/aspose.words.fonts/fontsettings/
---
## FontSettings class

Bir belge için yazı tipi ayarlarını belirtir.

```csharp
public class FontSettings
```

## yapıcılar

| İsim | Tanım |
| --- | --- |
| [FontSettings](fontsettings/)() | Default_Constructor |

## Özellikleri

| İsim | Tanım |
| --- | --- |
| static [DefaultInstance](../../aspose.words.fonts/fontsettings/defaultinstance/) { get; } | Statik varsayılan yazı tipi ayarları. |
| [FallbackSettings](../../aspose.words.fonts/fontsettings/fallbacksettings/) { get; } | Yazı tipi geri dönüş mekanizmasıyla ilgili ayarlar. |
| [SubstitutionSettings](../../aspose.words.fonts/fontsettings/substitutionsettings/) { get; } | Yazı tipi değiştirme mekanizmasıyla ilgili ayarlar. |

## yöntemler

| İsim | Tanım |
| --- | --- |
| [GetFontsSources](../../aspose.words.fonts/fontsettings/getfontssources/)() | Aspose.Words'ün TrueType yazı tiplerini aradığı kaynakların listesini içeren dizinin bir kopyasını alır. |
| [ResetFontSources](../../aspose.words.fonts/fontsettings/resetfontsources/)() | Yazı tipi kaynaklarını sistem varsayılanına sıfırlar. |
| [SaveSearchCache](../../aspose.words.fonts/fontsettings/savesearchcache/)(Stream) | Yazı tipi arama önbelleğini akışa kaydeder. |
| [SetFontsFolder](../../aspose.words.fonts/fontsettings/setfontsfolder/)(string, bool) | Aspose.Words'ün belgeleri oluştururken veya yazı tiplerini gömerken TrueType yazı tiplerini aradığı klasörü ayarlar. [`SetFontsFolders`](./setfontsfolders/) yalnızca bir yazı tipi dizini ayarlamak için. |
| [SetFontsFolders](../../aspose.words.fonts/fontsettings/setfontsfolders/)(string[], bool) | Aspose.Words'ün belgeleri oluştururken veya yazı tiplerini gömerken TrueType yazı tiplerini aradığı klasörleri ayarlar. |
| [SetFontsSources](../../aspose.words.fonts/fontsettings/setfontssources/#setfontssources)(FontSourceBase[]) | Aspose.Words'ün belgeleri oluştururken veya yazı tiplerini gömerken TrueType yazı tiplerini aradığı kaynakları ayarlar. |
| [SetFontsSources](../../aspose.words.fonts/fontsettings/setfontssources/#setfontssources_1)(FontSourceBase[], Stream) | Aspose.Words'ün TrueType yazı tiplerini aradığı kaynakları ayarlar ve ek olarak önceden kaydedilmiş yazı tipi arama önbelleğini yükler. |

### Notlar

Aspose.Words, belgedeki yazı tiplerini çözmek için yazı tipi ayarlarını kullanır. Yazı tipleri çoğunlukla belge layout oluştururken veya sabit sayfa biçimlerine dönüştürülürken çözülür. Ancak bazı formatlar yüklenirken Aspose.Words ayrıca yazı tiplerini çözmeyi gerektirebilir. Örneğin, Aspose.Words HTML belgeleri yüklediğinde, zaman font yedeği gerçekleştirmek için fontları çözebilir. Bu nedenle, in yazı tipi ayarlarını yapmanız önerilir.[`LoadOptions`](../../aspose.words.loading/loadoptions/) belgeyi yüklerken. Veya en azından düzeni oluşturmadan veya belgeyi sabit sayfa formatına dönüştürmeden önce.

Varsayılan olarak tüm belgeler tek bir statik yazı tipi ayarları örneğini kullanır. tarafından erişilebilir[`DefaultInstance`](./defaultinstance/) Emlak.

Yazı tipi ayarlarını değiştirmek, herhangi bir diziden herhangi bir zamanda güvenlidir. Ancak bu ayarları kullanan bazı belgeleri işlerken yazı tipi ayarlarını değiştirmemeniz önerilir. Bu, aynı yazı tipinin belgenin farklı bölümlerinde farklı şekilde çözümlenmesine neden olabilir.

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

Bir yazı tipi kaynak dizininin nasıl ayarlanacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Name = "Arvo";
builder.Writeln("Hello world!");
builder.Font.Name = "Amethysta";
builder.Writeln("The quick brown fox jumps over the lazy dog.");

// Yazı tipi kaynaklarımız, bu belgede metin için kullandığımız yazı tipini içermemektedir.
// Bu belgeyi render ederken bu font ayarlarını kullanırsak,
// Aspose.Words, Aspose.Words'ün bulamadığı bir yazı tipine sahip metne bir yedek yazı tipi uygulayacaktır.
FontSourceBase[] originalFontSources = FontSettings.DefaultInstance.GetFontsSources();

Assert.AreEqual(1, originalFontSources.Length);
Assert.True(originalFontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Arial"));

// Varsayılan yazı tipi kaynaklarında bu belgede kullandığımız iki yazı tipi eksik.
Assert.False(originalFontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Arvo"));
Assert.False(originalFontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Amethysta"));

// Yeni bir yazı tipi kaynağı olarak işlev görecek bir dizin ayarlamak için "SetFontsFolder" yöntemini kullanın.
// Dizindeki tüm yazı tipi dosyalarından yazı tiplerini dahil etmek için "özyinelemeli" argüman olarak "false" iletin
// ilk argümanda ilettiğimiz, ancak bu dizinin alt klasörlerinden herhangi birine herhangi bir yazı tipi dahil etmediğimizi.
// Geçtiğimiz dizindeki tüm yazı tipi dosyalarını dahil etmek için "özyinelemeli" argüman olarak "true" iletin
// ilk argümanda ve alt dizinlerindeki tüm yazı tiplerinde.
FontSettings.DefaultInstance.SetFontsFolder(FontsDir, recursive);

FontSourceBase[] newFontSources = FontSettings.DefaultInstance.GetFontsSources();

Assert.AreEqual(1, newFontSources.Length);
Assert.False(newFontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Arial"));
Assert.True(newFontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Arvo"));

// "Ametist" yazı tipi, yazı tipi dizininin bir alt klasöründedir.
if (recursive)
{
    Assert.AreEqual(25, newFontSources[0].GetAvailableFonts().Count);
    Assert.True(newFontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Amethysta"));
}
else
{
    Assert.AreEqual(18, newFontSources[0].GetAvailableFonts().Count);
    Assert.False(newFontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Amethysta"));
}

doc.Save(ArtifactsDir + "FontSettings.SetFontsFolder.pdf");

// Orijinal yazı tipi kaynaklarını geri yükleyin.
FontSettings.DefaultInstance.SetFontsSources(originalFontSources);
```

Birden çok yazı tipi kaynak dizininin nasıl ayarlanacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Name = "Amethysta";
builder.Writeln("The quick brown fox jumps over the lazy dog.");
builder.Font.Name = "Junction Light";
builder.Writeln("The quick brown fox jumps over the lazy dog.");

// Yazı tipi kaynaklarımız, bu belgede metin için kullandığımız yazı tipini içermemektedir.
// Bu belgeyi render ederken bu font ayarlarını kullanırsak,
// Aspose.Words, Aspose.Words'ün bulamadığı bir yazı tipine sahip metne bir yedek yazı tipi uygulayacaktır.
FontSourceBase[] originalFontSources = FontSettings.DefaultInstance.GetFontsSources();

Assert.AreEqual(1, originalFontSources.Length);
Assert.True(originalFontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Arial"));

// Varsayılan yazı tipi kaynaklarında bu belgede kullandığımız iki yazı tipi eksik.
Assert.False(originalFontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Amethysta"));
Assert.False(originalFontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Junction Light"));

// İlk argüman olarak ilettiğimiz her font dizininden bir font kaynağı oluşturmak için "SetFontsFolders" yöntemini kullanın.
// Dizinlerdeki tüm font dosyalarından fontları dahil etmek için "özyinelemeli" argüman olarak "false" iletin
// ilk argümanda geçiyoruz, ancak dizinlerin alt klasörlerinden herhangi bir yazı tipini dahil etmiyoruz.
// Geçtiğimiz dizinlerdeki tüm yazı tipi dosyalarını dahil etmek için "özyinelemeli" argüman olarak "true" iletin
// ilk argümanda ve alt dizinlerindeki tüm yazı tiplerinde.
FontSettings.DefaultInstance.SetFontsFolders(new[] {FontsDir + "/Amethysta", FontsDir + "/Junction"},
    recursive);

FontSourceBase[] newFontSources = FontSettings.DefaultInstance.GetFontsSources();

Assert.AreEqual(2, newFontSources.Length);
Assert.False(newFontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Arial"));
Assert.AreEqual(1, newFontSources[0].GetAvailableFonts().Count);
Assert.True(newFontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Amethysta"));

// "Junction" klasörünün kendisi yazı tipi dosyası içermez, ancak bunu yapan alt klasörlere sahiptir.
if (recursive)
{
    Assert.AreEqual(6, newFontSources[1].GetAvailableFonts().Count);
    Assert.True(newFontSources[1].GetAvailableFonts().Any(f => f.FullFontName == "Junction Light"));
}
else
{
    Assert.AreEqual(0, newFontSources[1].GetAvailableFonts().Count);
}

doc.Save(ArtifactsDir + "FontSettings.SetFontsFolders.pdf");

// Orijinal yazı tipi kaynaklarını geri yükleyin.
FontSettings.DefaultInstance.SetFontsSources(originalFontSources);
```

### Ayrıca bakınız

* ad alanı [Aspose.Words.Fonts](../../aspose.words.fonts/)
* toplantı [Aspose.Words](../../)


