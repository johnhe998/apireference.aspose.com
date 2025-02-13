---
title: HtmlSaveOptions.FontResourcesSubsettingSizeThreshold
second_title: Aspose.Words for .NET API Referansı
description: HtmlSaveOptions mülk. HTML MHTML veya EPUBa kaydederken hangi yazı tipi kaynaklarının alt ayarlanması gerektiğini kontrol eder. Varsayılan0 .
type: docs
weight: 300
url: /tr/net/aspose.words.saving/htmlsaveoptions/fontresourcessubsettingsizethreshold/
---
## HtmlSaveOptions.FontResourcesSubsettingSizeThreshold property

HTML, MHTML veya EPUB'a kaydederken hangi yazı tipi kaynaklarının alt ayarlanması gerektiğini kontrol eder. Varsayılan`0` .

```csharp
public int FontResourcesSubsettingSizeThreshold { get; set; }
```

### Notlar

[`ExportFontResources`](../exportfontresources/) yazı tiplerini yardımcı dosyalar olarak veya output paketinin parçaları olarak dışa aktarmaya izin verir. Belge, özellikle çok sayıda glif içeren birçok yazı tipi kullanıyorsa, çıktı boyutu önemli ölçüde artabilir . Yazı tipi alt kümesi, geçerli belge tarafından kullanılmayan gliflerini filtreleyerek dışa aktarılan yazı tipi kaynağının boyutunu azaltır.

Yazı tipi alt kümesi aşağıdaki gibi çalışır:

* Varsayılan olarak, dışa aktarılan tüm yazı tipleri alt kümelenir.
* Ayar`FontResourcesSubsettingSizeThreshold`pozitif bir değere , Aspose.Words'e, dosya boyutu belirtilen değerden daha büyük olan yazı tiplerini alt kümeler için talimat verir.
* Özelliğin ayarlanmasıMaxValue yazı tipi alt kümesini bastırır.

**Önemli!** Yazı tipi kaynaklarını dışa aktarırken, yazı tipi lisanslama sorunları dikkate alınmalıdır. İndirilebilir yazı tipi mekanizması aracılığıyla belirli yazı tiplerini kullanmak isteyen yazarlar, kullanım amaçlarının yazı tipi lisansı kapsamında olduğunu her zaman dikkatli bir şekilde doğrulamalıdır. Şu anda birçok ticari yazı tipi, yazı tiplerinin herhangi bir biçimde web'den indirilmesine izin vermemektedir. Bazı yazı tiplerini kapsayan lisans sözleşmeleri, özellikle **@ yazı tipi-yüz** CSS stil sayfalarında kurallar 'ye izin verilmez. Yazı tipi alt kümesi, lisans koşullarını da ihlal edebilir.

### Örnekler

Yazı tipi alt kümesiyle nasıl çalışılacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Name = "Arial";
builder.Writeln("Hello world!");
builder.Font.Name = "Times New Roman";
builder.Writeln("Hello world!");
builder.Font.Name = "Courier New";
builder.Writeln("Hello world!");

// Belgeyi HTML'ye kaydettiğimizde, bir SaveOptions nesne yapılandırma yazı tipi alt kümesini geçirebiliriz.
// "ExportFontResources" bayrağını "true" olarak ayarladığımızı ve ayrıca "FontsFolder" özelliğinde bir klasöre isim verdiğimizi varsayalım.
// Bu durumda, kaydetme işlemi o klasörü oluşturacak ve içine bir .ttf dosyası yerleştirecektir.
// belgemizin kullandığı her yazı tipi için bu klasör.
// Her .ttf dosyası, o yazı tipinin tüm glif kümesini içerecektir,
// potansiyel olarak belgeye eşlik eden çok büyük bir dosyayla sonuçlanabilir.
// Bir yazı tipine alt küme uyguladığımızda, dışa aktarılan ham verileri yalnızca belgenin olduğu glifleri içerecektir.
// glif kümesinin tamamı yerine kullanılıyor. Belgemizdeki metin bir yazı tipinin yalnızca küçük bir bölümünü kullanıyorsa
// glif kümesi, ardından alt kümeleme çıktı belgelerimizin boyutunu önemli ölçüde azaltır.
// Bir .ttf dosya boyutunu bayt olarak tanımlamak için "FontResourcesSubsettingSizeThreshold" özelliğini kullanabiliriz.
 // Dışa aktarılan bir yazı tipi bundan daha büyük bir dosya oluşturursa, kaydetme işlemi bu yazı tipine alt küme uygular.
// 0 eşiğinin ayarlanması, tüm yazı tiplerine alt kümeleme uygular,
// ve onu "int.MaxValue" olarak ayarlamak, alt kümelemeyi etkin bir şekilde devre dışı bırakır.
string fontsFolder = ArtifactsDir + "HtmlSaveOptions.FontSubsetting.Fonts";

HtmlSaveOptions options = new HtmlSaveOptions
{
    ExportFontResources = true,
    FontsFolder = fontsFolder,
    FontResourcesSubsettingSizeThreshold = fontResourcesSubsettingSizeThreshold
};

doc.Save(ArtifactsDir + "HtmlSaveOptions.FontSubsetting.html", options);

string[] fontFileNames = Directory.GetFiles(fontsFolder).Where(s => s.EndsWith(".ttf")).ToArray();

Assert.AreEqual(3, fontFileNames.Length);

foreach (string filename in fontFileNames)
{
    // Varsayılan olarak, üç yazı tipimizin her biri için .ttf dosyaları 700 MB'ın üzerinde olacaktır.
    // Alt kümeleme, hepsini 30 MB'ın altına indirecektir.
    FileInfo fontFileInfo = new FileInfo(filename);

    Assert.True(fontFileInfo.Length > 700000 || fontFileInfo.Length < 30000);
    Assert.True(Math.Max(fontResourcesSubsettingSizeThreshold, 30000) > new FileInfo(filename).Length);
}
```

### Ayrıca bakınız

* class [HtmlSaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../htmlsaveoptions/)
* toplantı [Aspose.Words](../../../)


