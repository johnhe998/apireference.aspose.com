---
title: FontSourceBase.WarningCallback
second_title: Aspose.Words for .NET API Referansı
description: FontSourceBase mülk. Biçimlendirme aslına uygunluk kaybına neden olabilecek bir sorun algılandığında yazı tipi kaynağının işlenmesi sırasında çağrılır.
type: docs
weight: 30
url: /tr/net/aspose.words.fonts/fontsourcebase/warningcallback/
---
## FontSourceBase.WarningCallback property

Biçimlendirme aslına uygunluk kaybına neden olabilecek bir sorun algılandığında yazı tipi kaynağının işlenmesi sırasında çağrılır.

```csharp
public IWarningCallback WarningCallback { get; set; }
```

### Örnekler

Yazı tipi kaynakları ile çalışırken uyarının nasıl geri çağrılacağını gösterir.

```csharp
[Test]
public void FontSourceWarning()
{
    FontSettings settings = new FontSettings();
    settings.SetFontsFolder("bad folder?", false);

    FontSourceBase source = settings.GetFontsSources()[0];
    FontSourceWarningCollector callback = new FontSourceWarningCollector();
    source.WarningCallback = callback;

    // Uyarıyı geri çağırmak için yazı tiplerinin listesini alın.
    IList<PhysicalFontInfo> fontInfos = source.GetAvailableFonts();

    Assert.True(callback.FontSubstitutionWarnings[0].Description
        .Contains("Error loading font from the folder \"bad folder?\""));
}

private class FontSourceWarningCollector : IWarningCallback
{
    /// <summary>
    /// Font kaynağının işlenmesi sırasında her uyarı oluştuğunda çağrılır.
    /// </summary>
    public void Warning(WarningInfo info)
    {
        FontSubstitutionWarnings.Warning(info);
    }

    public readonly WarningInfoCollection FontSubstitutionWarnings = new WarningInfoCollection();
}
```

### Ayrıca bakınız

* interface [IWarningCallback](../../../aspose.words/iwarningcallback/)
* class [FontSourceBase](../)
* ad alanı [Aspose.Words.Fonts](../../fontsourcebase/)
* toplantı [Aspose.Words](../../../)


