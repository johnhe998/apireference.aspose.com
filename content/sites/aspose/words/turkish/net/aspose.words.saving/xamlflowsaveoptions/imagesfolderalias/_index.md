---
title: XamlFlowSaveOptions.ImagesFolderAlias
second_title: Aspose.Words for .NET API Referansı
description: XamlFlowSaveOptions mülk. Bir XAML belgesine yazılan görüntü URIlerini oluşturmak için kullanılan klasörün adını belirtir. Varsayılan boş bir dizedir.
type: docs
weight: 40
url: /tr/net/aspose.words.saving/xamlflowsaveoptions/imagesfolderalias/
---
## XamlFlowSaveOptions.ImagesFolderAlias property

Bir XAML belgesine yazılan görüntü URI'lerini oluşturmak için kullanılan klasörün adını belirtir. Varsayılan boş bir dizedir.

```csharp
public string ImagesFolderAlias { get; set; }
```

### Notlar

Bir kaydettiğinizde[`Document`](../../../aspose.words/document/) XAML formatında Aspose.Words'ün belgeye gömülü tüm resimleri bağımsız dosyalar olarak kaydetmesi gerekir.[`ImagesFolder`](../imagesfolder/) , görüntülerin nereye kaydedileceğini belirlemenize ve`ImagesFolderAlias` , görüntü URI'lerinin nasıl oluşturulacağını belirlemeye izin verir.

Eğer`ImagesFolderAlias` boş bir dize değilse, XAML'ye yazılan görüntü URI'siImagesFolderAlias + &lt;görüntü dosyası adı&gt;.

Eğer`ImagesFolderAlias` boş bir dizeyse, XAML'ye yazılmış görüntü URI'si şöyle olur:ImagesFolder + &lt;görüntü dosyası adı&gt;.

Eğer`ImagesFolderAlias` ayarlandı '.' (nokta), ardından görüntü dosyası adı, diğer seçeneklerden bağımsız olarak yol olmadan XAML'ye yazılır.

### Örnekler

Bir belgeyi akış formu .xaml'e dönüştürürken oluşturulan bağlantılı görüntülerin dosya adlarının nasıl yazdırılacağını gösterir.

```csharp
{
    Document doc = new Document(MyDir + "Rendering.docx");

    ImageUriPrinter callback = new ImageUriPrinter(ArtifactsDir + "XamlFlowImageFolderAlias");

    // Belgenin "Kaydet" yöntemine aktarabileceğimiz bir "XamlFlowSaveOptions" nesnesi oluşturun
    // belgeyi XAML kaydetme biçimine kaydetme biçimimizi değiştirmek için.
    XamlFlowSaveOptions options = new XamlFlowSaveOptions();

    Assert.AreEqual(SaveFormat.XamlFlow, options.SaveFormat);

    // Yerel dosya sisteminde içine bir klasör atamak için "ImagesFolder" özelliğini kullanın.
    // Aspose.Words tüm dokümanın bağlantılı resimlerini kaydedecektir.
    options.ImagesFolder = ArtifactsDir + "XamlFlowImageFolder";

    // Bu klasörü kullanmak için "ImagesFolderAlias" özelliğini kullanın
    // görüntüler klasörünün adı yerine görüntü URI'leri oluşturulurken.
    options.ImagesFolderAlias = ArtifactsDir + "XamlFlowImageFolderAlias";

    options.ImageSavingCallback = callback;

    // "ImagesFolderAlias" tarafından belirtilen bir klasörün "ImagesFolder" yerine kaynakları içermesi gerekir.
    // Geri aramanın akışları kaynaklarını içine koyabilmeden önce klasörün var olduğundan emin olmalıyız.
    Directory.CreateDirectory(options.ImagesFolderAlias);

    doc.Save(ArtifactsDir + "XamlFlowSaveOptions.ImageFolder.xaml", options);

    foreach (string resource in callback.Resources)
        Console.WriteLine($"{callback.ImagesFolderAlias}/{resource}");

/// <summary>
/// Üst belgeleri akış formu .xaml'e dönüştürülürken görüntülerin dosya adlarını sayar ve yazdırır.
/// </summary>
private class ImageUriPrinter : IImageSavingCallback
{
    public ImageUriPrinter(string imagesFolderAlias)
    {
        ImagesFolderAlias = imagesFolderAlias;
        Resources = new List<string>();
    }

    void IImageSavingCallback.ImageSaving(ImageSavingArgs args)
    {
        Resources.Add(args.ImageFileName);

        // Bir resim klasörü takma adı belirtseydik, ayrıca
        // imajını takma ad klasörüne koymak için her akışı yeniden yönlendirmek için.
        args.ImageStream = new FileStream($"{ImagesFolderAlias}/{args.ImageFileName}", FileMode.Create);
        args.KeepImageStreamOpen = false;
    }

    public string ImagesFolderAlias { get; }
    public List<string> Resources { get; }
}
```

### Ayrıca bakınız

* class [XamlFlowSaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../xamlflowsaveoptions/)
* toplantı [Aspose.Words](../../../)


