---
title: XamlFixedSaveOptions.ResourcesFolderAlias
second_title: Aspose.Words for .NET API Referansı
description: XamlFixedSaveOptions mülk. Sabit bir sayfa Xaml belgesine yazılan görüntü URIlerini oluşturmak için kullanılan klasörün adını belirtir. Varsayılanhükümsüz .
type: docs
weight: 40
url: /tr/net/aspose.words.saving/xamlfixedsaveoptions/resourcesfolderalias/
---
## XamlFixedSaveOptions.ResourcesFolderAlias property

Sabit bir sayfa Xaml belgesine yazılan görüntü URI'lerini oluşturmak için kullanılan klasörün adını belirtir. Varsayılan`hükümsüz` .

```csharp
public string ResourcesFolderAlias { get; set; }
```

### Notlar

Bir kaydettiğinizde[`Document`](../../../aspose.words/document/) Sabit sayfa Xaml formatında Aspose.Words'ün belgeye gömülü tüm resimleri bağımsız dosyalar olarak kaydetmesi gerekir.[`ResourcesFolder`](../resourcesfolder/) , görüntülerin nereye kaydedileceğini belirlemenize ve`ResourcesFolderAlias` , görüntü URI'lerinin nasıl oluşturulacağını belirlemeye izin verir.

### Örnekler

Bir belgeyi sabit biçimli .xaml'e dönüştürürken oluşturulan bağlantılı kaynakların URI'lerinin nasıl yazdırılacağını gösterir.

```csharp
public void ResourceFolder()
{
    Document doc = new Document(MyDir + "Rendering.docx");
    ResourceUriPrinter callback = new ResourceUriPrinter();

    // Belgenin "Kaydet" yöntemine geçebileceğimiz bir "XamlFixedSaveOptions" nesnesi oluşturun
    // belgeyi XAML kaydetme biçimine kaydetme biçimimizi değiştirmek için.
    XamlFixedSaveOptions options = new XamlFixedSaveOptions();

    Assert.AreEqual(SaveFormat.XamlFixed, options.SaveFormat);

    // Yerel dosya sisteminde içine bir klasör atamak için "ResourcesFolder" özelliğini kullanın.
    // Aspose.Words, resimler ve yazı tipleri gibi belgenin bağlantılı tüm kaynaklarını kaydeder.
    options.ResourcesFolder = ArtifactsDir + "XamlFixedResourceFolder";

    // Bu klasörü kullanmak için "ResourcesFolderAlias" özelliğini kullanın
    // kaynaklar klasörünün adı yerine görüntü URI'leri oluşturulurken.
    options.ResourcesFolderAlias = ArtifactsDir + "XamlFixedFolderAlias";

    options.ResourceSavingCallback = callback;

    // "ResourcesFolderAlias" tarafından belirtilen bir klasörün "ResourcesFolder" yerine kaynakları içermesi gerekir.
    // Geri aramanın akışları kaynaklarını içine koyabilmeden önce klasörün var olduğundan emin olmalıyız.
    Directory.CreateDirectory(options.ResourcesFolderAlias);

    doc.Save(ArtifactsDir + "XamlFixedSaveOptions.ResourceFolder.xaml", options);

    foreach (string resource in callback.Resources)
        Console.WriteLine(resource);
}

/// <summary>
/// Sabit .xaml'e dönüştürme sırasında oluşturulan kaynakların URI'lerini sayar ve yazdırır.
/// </summary>
private class ResourceUriPrinter : IResourceSavingCallback
{
    public ResourceUriPrinter()
    {
        Resources = new List<string>();
    }

    void IResourceSavingCallback.ResourceSaving(ResourceSavingArgs args)
    {
        Resources.Add($"Resource \"{args.ResourceFileName}\"\n\t{args.ResourceFileUri}");

        // Bir kaynak klasör takma adı belirtseydik, ayrıca
        // her akışı, kaynağını takma ad klasörüne koymak için yeniden yönlendirmek için.
        args.ResourceStream = new FileStream(args.ResourceFileUri, FileMode.Create);
        args.KeepResourceStreamOpen = false;
    }

    public List<string> Resources { get; }
}
```

### Ayrıca bakınız

* class [XamlFixedSaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../xamlfixedsaveoptions/)
* toplantı [Aspose.Words](../../../)


