---
title: Class CssSavingArgs
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Saving.CssSavingArgs sınıf. için veri sağlarCssSaving olay.
type: docs
weight: 4620
url: /tr/net/aspose.words.saving/csssavingargs/
---
## CssSavingArgs class

için veri sağlar[`CssSaving`](../icsssavingcallback/csssaving/) olay.

```csharp
public class CssSavingArgs
```

## Özellikleri

| İsim | Tanım |
| --- | --- |
| [CssStream](../../aspose.words.saving/csssavingargs/cssstream/) { get; set; } | CSS bilgilerinin kaydedileceği akışı belirlemeye izin verir. |
| [Document](../../aspose.words.saving/csssavingargs/document/) { get; } | Şu anda kaydedilmekte olan belge nesnesini alır. |
| [IsExportNeeded](../../aspose.words.saving/csssavingargs/isexportneeded/) { get; set; } | CSS'nin dosyaya dışa aktarılıp aktarılmayacağını ve HTML belgesine gömüleceğini belirlemeye izin verir. Varsayılan`doğru` . Bu özellik`yanlış` , CSS bilgileri bir CSS dosyasına kaydedilmeyecek ve HTML belgesine gömülmeyecektir. |
| [KeepCssStreamOpen](../../aspose.words.saving/csssavingargs/keepcssstreamopen/) { get; set; } | Aspose.Words'ün bir CSS bilgisi kaydettikten sonra akışı açık tutması mı yoksa kapatması mı gerektiğini belirtir. |

### Notlar

Aspose.Words varsayılan olarak bir belgeyi HTML'ye kaydettiğinde, CSS bilgisini inline (bir **stil** her öğede öznitelik).

`CssSavingArgs` kendi akış nesnenizi sağlayarak CSS bilgilerini dosyaya kaydetmenize izin verir.

CSS'yi akışa kaydetmek için[`CssStream`](./cssstream/) Emlak.

CSS'yi bir dosyaya kaydetmeyi ve HTML belgesine gömmeyi bastırmak için[`IsExportNeeded`](./isexportneeded/) Emlak.

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


