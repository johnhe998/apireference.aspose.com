---
title: Interface ICssSavingCallback
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Saving.ICssSavingCallback arayüz. Aspose.Wordsün bir belgeyi HTMLye kaydederken CSSyi Cascading Style Sheet nasıl kaydettiğini kontrol etmek istiyorsanız bu arayüzü uygulayın.
type: docs
weight: 4870
url: /tr/net/aspose.words.saving/icsssavingcallback/
---
## ICssSavingCallback interface

Aspose.Words'ün bir belgeyi HTML'ye kaydederken CSS'yi (Cascading Style Sheet) nasıl kaydettiğini kontrol etmek istiyorsanız bu arayüzü uygulayın.

```csharp
public interface ICssSavingCallback
```

## yöntemler

| İsim | Tanım |
| --- | --- |
| [CssSaving](../../aspose.words.saving/icsssavingcallback/csssaving/)(CssSavingArgs) | Aspose.Words bir CSS (Cascading Style Sheet) kaydettiğinde çağrılır. |

### Örnekler

Bir HTML dönüşümünün oluşturduğu CSS stil sayfalarıyla nasıl çalışılacağını gösterir.

```csharp
public void ExternalCssFilenames()
{
    Document doc = new Document(MyDir + "Rendering.docx");

    // Belgenin "Kaydet" yöntemine aktarabileceğimiz bir "HtmlFixedSaveOptions" nesnesi oluşturun
    // belgeyi HTML'ye nasıl dönüştüreceğimizi değiştirmek için.
    HtmlSaveOptions options = new HtmlSaveOptions();

    // "CssStylesheetType" özelliğini "CssStyleSheetType.External" olarak ayarlayın.
    // kaydedilmiş bir HTML belgesine harici bir CSS stil sayfası dosyasıyla eşlik edin.
    options.CssStyleSheetType = CssStyleSheetType.External;

    // Aşağıda, çıktı CSS stil sayfaları için dizinleri ve dosya adlarını belirtmenin iki yolu bulunmaktadır.
    // 1 - Stil sayfamıza bir dosya adı atamak için "CssStyleSheetFileName" özelliğini kullanın:
    options.CssStyleSheetFileName = ArtifactsDir + "SavingCallback.ExternalCssFilenames.css";

    // 2 - Stil sayfamızı adlandırmak için özel bir geri arama kullanın:
    options.CssSavingCallback =
        new CustomCssSavingCallback(ArtifactsDir + "SavingCallback.ExternalCssFilenames.css", true, false);

    doc.Save(ArtifactsDir + "SavingCallback.ExternalCssFilenames.html", options);
}

/// <summary>
/// Harici bir CSS stil sayfası için diğer parametrelerle birlikte özel bir dosya adı ayarlar.
/// </summary>
private class CustomCssSavingCallback : ICssSavingCallback
{
    public CustomCssSavingCallback(string cssDocFilename, bool isExportNeeded, bool keepCssStreamOpen)
    {
        mCssTextFileName = cssDocFilename;
        mIsExportNeeded = isExportNeeded;
        mKeepCssStreamOpen = keepCssStreamOpen;
    }

    public void CssSaving(CssSavingArgs args)
    {
        // "Document" özelliği ile kaynak belgenin tamamına erişebiliriz.
        Assert.True(args.Document.OriginalFileName.EndsWith("Rendering.docx"));

        args.CssStream = new FileStream(mCssTextFileName, FileMode.Create);
        args.IsExportNeeded = mIsExportNeeded;
        args.KeepCssStreamOpen = mKeepCssStreamOpen;

        Assert.True(args.CssStream.CanWrite);
    }

    private readonly string mCssTextFileName;
    private readonly bool mIsExportNeeded;
    private readonly bool mKeepCssStreamOpen;
}
```

### Ayrıca bakınız

* ad alanı [Aspose.Words.Saving](../../aspose.words.saving/)
* toplantı [Aspose.Words](../../)


