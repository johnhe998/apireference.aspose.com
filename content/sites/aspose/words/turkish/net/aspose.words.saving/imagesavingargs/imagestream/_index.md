---
title: ImageSavingArgs.ImageStream
second_title: Aspose.Words for .NET API Referansı
description: ImageSavingArgs mülk. Resmin kaydedileceği akışı belirlemeye izin verir.
type: docs
weight: 40
url: /tr/net/aspose.words.saving/imagesavingargs/imagestream/
---
## ImageSavingArgs.ImageStream property

Resmin kaydedileceği akışı belirlemeye izin verir.

```csharp
public Stream ImageStream { get; set; }
```

### Notlar

Bu özellik, HTML sırasında dosyalar yerine görüntüleri akışlara kaydetmenize olanak tanır.

Varsayılan değer`hükümsüz` . Bu özellik ne zaman`hükümsüz` , resmi, belirtilen bir dosyaya kaydedilecektir.[`ImageFileName`](../imagefilename/) Emlak.

kullanma[`IImageSavingCallback`](../../iimagesavingcallback/) bir resmi başka bir ile değiştiremezsiniz. Yalnızca görüntülerin kaydedileceği konumun kontrolü için tasarlanmıştır.

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


