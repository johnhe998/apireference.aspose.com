---
title: Class PageSavingArgs
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Saving.PageSavingArgs sınıf. için veri sağlarPageSaving olay.
type: docs
weight: 5100
url: /tr/net/aspose.words.saving/pagesavingargs/
---
## PageSavingArgs class

için veri sağlar[`PageSaving`](../ipagesavingcallback/pagesaving/) olay.

```csharp
public class PageSavingArgs
```

## yapıcılar

| İsim | Tanım |
| --- | --- |
| [PageSavingArgs](pagesavingargs/)() | Default_Constructor |

## Özellikleri

| İsim | Tanım |
| --- | --- |
| [KeepPageStreamOpen](../../aspose.words.saving/pagesavingargs/keeppagestreamopen/) { get; set; } | Aspose.Words'ün bir belge sayfasını kaydettikten sonra akışı açık tutması mı yoksa kapatması mı gerektiğini belirtir. |
| [PageFileName](../../aspose.words.saving/pagesavingargs/pagefilename/) { get; set; } | Belge sayfasının kaydedileceği dosya adını alır veya ayarlar. |
| [PageIndex](../../aspose.words.saving/pagesavingargs/pageindex/) { get; } | Geçerli sayfa dizini. |
| [PageStream](../../aspose.words.saving/pagesavingargs/pagestream/) { get; set; } | Belge sayfasının kaydedileceği akışı belirtmeye izin verir. |

### Örnekler

Bir belgeyi sayfa sayfa HTML'ye kaydetmek için bir geri aramanın nasıl kullanılacağını gösterir.

```csharp
public void PageFileNames()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.Writeln("Page 1.");
    builder.InsertBreak(BreakType.PageBreak);
    builder.Writeln("Page 2.");
    builder.InsertImage(ImageDir + "Logo.jpg");
    builder.InsertBreak(BreakType.PageBreak);
    builder.Writeln("Page 3.");

    // Belgenin "Kaydet" yöntemine aktarabileceğimiz bir "HtmlFixedSaveOptions" nesnesi oluşturun
    // belgeyi HTML'ye nasıl dönüştüreceğimizi değiştirmek için.
    HtmlFixedSaveOptions htmlFixedSaveOptions = new HtmlFixedSaveOptions();

    // Bu belgedeki her sayfayı yerel dosya sisteminde ayrı bir HTML dosyasına kaydedeceğiz.
    // Her çıktı HTML belgesini adlandırmamıza izin veren bir geri arama ayarlayın.
    htmlFixedSaveOptions.PageSavingCallback = new CustomFileNamePageSavingCallback();

    doc.Save(ArtifactsDir + "SavingCallback.PageFileNames.html", htmlFixedSaveOptions);

    string[] filePaths = Directory.GetFiles(ArtifactsDir).Where(
        s => s.StartsWith(ArtifactsDir + "SavingCallback.PageFileNames.Page_")).OrderBy(s => s).ToArray();

    Assert.AreEqual(3, filePaths.Length);
}

/// <summary>
/// Tüm sayfaları içinde belirtilen bir dosya ve dizine kaydeder.
/// </summary>
private class CustomFileNamePageSavingCallback : IPageSavingCallback
{
    public void PageSaving(PageSavingArgs args)
    {
        string outFileName = $"{ArtifactsDir}SavingCallback.PageFileNames.Page_{args.PageIndex}.html";

        // Aspose.Words'ün belgenin her sayfasını nereye kaydedeceğini belirlemenin iki yolu aşağıdadır.
        // 1 - Çıktı sayfası dosyası için bir dosya adı belirleyin:
        args.PageFileName = outFileName;

        // 2 - Çıktı sayfası dosyası için özel bir akış oluşturun:
        args.PageStream = new FileStream(outFileName, FileMode.Create);

        Assert.False(args.KeepPageStreamOpen);
    }
}
```

### Ayrıca bakınız

* ad alanı [Aspose.Words.Saving](../../aspose.words.saving/)
* toplantı [Aspose.Words](../../)


