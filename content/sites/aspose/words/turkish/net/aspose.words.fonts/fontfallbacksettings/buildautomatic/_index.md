---
title: FontFallbackSettings.BuildAutomatic
second_title: Aspose.Words for .NET API Referansı
description: FontFallbackSettings yöntem. Kullanılabilir yazı tiplerini tarayarak yedek ayarları otomatik olarak oluşturur.
type: docs
weight: 10
url: /tr/net/aspose.words.fonts/fontfallbacksettings/buildautomatic/
---
## FontFallbackSettings.BuildAutomatic method

Kullanılabilir yazı tiplerini tarayarak yedek ayarları otomatik olarak oluşturur.

```csharp
public void BuildAutomatic()
```

### Notlar

Bu yöntem, optimum olmayan geri dönüş ayarları üretebilir. Yazı tipleri tarafından kontrol edilir[ Unicode Karakter Aralığı](https://docs.microsoft.com/en-us/typography/opentype/spec/os2#ur) alanlar ve gerçek gliflerin varlığı ile değil. Ayrıca Unicode aralıkları ayrı ayrı kontrol edilir ve tek bir dil/komut dosyasıyla ilgili çeşitli aralıklar farklı yedek yazı tipleri kullanabilir.

### Örnekler

Unicode karakter kod aralıkları arasında yedek yazı tiplerinin nasıl dağıtılacağını gösterir.

```csharp
Document doc = new Document();

FontSettings fontSettings = new FontSettings();
doc.FontSettings = fontSettings;
FontFallbackSettings fontFallbackSettings = fontSettings.FallbackSettings;

// Font ayarlarımızı sadece "MyFonts" klasöründen fontları kaynaklayacak şekilde yapılandırın.
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, false);
fontSettings.SetFontsSources(new FontSourceBase[] {folderFontSource});

// "BuildAutomatic" yöntemini çağırmak, bir geri dönüş şeması oluşturacaktır.
// erişilebilir yazı tiplerini mümkün olduğu kadar çok Unicode karakter koduna dağıtır.
// Bizim durumumuzda, "MyFonts" klasörü içindeki yalnızca bir avuç yazı tipine erişimi vardır.
fontFallbackSettings.BuildAutomatic();
fontFallbackSettings.Save(ArtifactsDir + "FontSettings.FallbackSettingsCustom.BuildAutomatic.xml");

// Bunun gibi bir dosyadan özel bir ikame şeması da yükleyebiliriz.
// Bu şema, "0000-00ff" Unicode blokları boyunca "AllegroOpen" yazı tipini, "0100-024f" boyunca "AllegroOpen" yazı tipini uygular,
// ve şemadaki diğer yazı tiplerinin kapsamadığı diğer tüm aralıklardaki "M+ 2m" yazı tipi.
fontFallbackSettings.Load(MyDir + "Custom font fallback settings.xml");

// Bir belge oluşturucu oluşturun ve yazı tipini hiçbir kaynağımızda bulunmayan bir yazı tipine ayarlayın.
// Yazı tipi ayarlarımız, mevcut olmayan yazı tipini kullanarak yazdığımız karakterler için geri dönüş şemasını çağıracaktır.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Missing Font";

// 0x0021'den 0x052F'ye kadar her Unicode karakterini yazdırmak için oluşturucuyu kullanın,
// özel yazı tipi geri dönüş şemamızda tanımladığımız Unicode bloklarını bölen açıklayıcı çizgilerle.
for (int i = 0x0021; i < 0x0530; i++)
{
    switch (i)
    {
        case 0x0021:
            builder.Writeln(
                "\n\n0x0021 - 0x00FF: \nBasic Latin/Latin-1 Supplement Unicode blocks in \"AllegroOpen\" font:");
            break;
        case 0x0100:
            builder.Writeln(
                "\n\n0x0100 - 0x024F: \nLatin Extended A/B blocks, mostly in \"AllegroOpen\" font:");
            break;
        case 0x0250:
            builder.Writeln("\n\n0x0250 - 0x052F: \nIPA/Greek/Cyrillic blocks in \"M+ 2m\" font:");
            break;
    }

    builder.Write($"{Convert.ToChar(i)}");
}

doc.Save(ArtifactsDir + "FontSettings.FallbackSettingsCustom.pdf");
```

### Ayrıca bakınız

* class [FontFallbackSettings](../)
* ad alanı [Aspose.Words.Fonts](../../fontfallbacksettings/)
* toplantı [Aspose.Words](../../../)


