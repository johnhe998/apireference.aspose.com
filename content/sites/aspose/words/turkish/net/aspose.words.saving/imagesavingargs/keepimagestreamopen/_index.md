---
title: ImageSavingArgs.KeepImageStreamOpen
second_title: Aspose.Words for .NET API Referansı
description: ImageSavingArgs mülk. Aspose.Wordsün bir görüntüyü kaydettikten sonra akışı açık tutması mı yoksa kapatması mı gerektiğini belirtir.
type: docs
weight: 60
url: /tr/net/aspose.words.saving/imagesavingargs/keepimagestreamopen/
---
## ImageSavingArgs.KeepImageStreamOpen property

Aspose.Words'ün bir görüntüyü kaydettikten sonra akışı açık tutması mı yoksa kapatması mı gerektiğini belirtir.

```csharp
public bool KeepImageStreamOpen { get; set; }
```

### Notlar

Varsayılan`yanlış` ve Aspose.Words, sağladığınız akışı [`ImageStream`](../imagestream/) içine bir resim yazdıktan sonra özellik. Belirtin`doğru` akışı açık tutmak için.

### Örnekler

Bir HTML dönüştürme işlemine bir resim kaydetme geri aramasının nasıl dahil edileceğini gösterir.

```csharp
{
    Document doc = new Document(MyDir + "Rendering.docx");

    // Belgeyi HTML'ye kaydettiğimizde, bir geri arama atamak için bir SaveOptions nesnesi iletebiliriz
    // görüntü kaydetme işlemini özelleştirmek için.
    HtmlSaveOptions options = new HtmlSaveOptions();
    options.ImageSavingCallback = new ImageShapePrinter();

    doc.Save(ArtifactsDir + "HtmlSaveOptions.ImageSavingCallback.html", options);
}

/// <summary>
/// Kaydetme işlemi yerel dosya sistemindeki bir görüntü dosyasına kaydederken her görüntünün özelliklerini yazdırır
/// bir belgenin HTML'ye aktarılması sırasında.
/// </summary>
private class ImageShapePrinter : IImageSavingCallback
{
    void IImageSavingCallback.ImageSaving(ImageSavingArgs args)
    {
        args.KeepImageStreamOpen = false;
        Assert.True(args.IsImageAvailable);

        Console.WriteLine($"{args.Document.OriginalFileName.Split('\\').Last()} Image #{++mImageCount}");

        LayoutCollector layoutCollector = new LayoutCollector(args.Document);

        Console.WriteLine($"\tOn page:\t{layoutCollector.GetStartPageIndex(args.CurrentShape)}");
        Console.WriteLine($"\tDimensions:\t{args.CurrentShape.Bounds}");
        Console.WriteLine($"\tAlignment:\t{args.CurrentShape.VerticalAlignment}");
        Console.WriteLine($"\tWrap type:\t{args.CurrentShape.WrapType}");
        Console.WriteLine($"Output filename:\t{args.ImageFileName}\n");
    }

    private int mImageCount;
}
```

### Ayrıca bakınız

* class [ImageSavingArgs](../)
* ad alanı [Aspose.Words.Saving](../../imagesavingargs/)
* toplantı [Aspose.Words](../../../)


