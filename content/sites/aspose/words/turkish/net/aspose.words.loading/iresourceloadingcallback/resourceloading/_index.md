---
title: IResourceLoadingCallback.ResourceLoading
second_title: Aspose.Words for .NET API Referansı
description: IResourceLoadingCallback yöntem. Aspose.Words herhangi bir harici kaynak yüklediğinde çağrılır.
type: docs
weight: 10
url: /tr/net/aspose.words.loading/iresourceloadingcallback/resourceloading/
---
## IResourceLoadingCallback.ResourceLoading method

Aspose.Words herhangi bir harici kaynak yüklediğinde çağrılır.

```csharp
public ResourceLoadingAction ResourceLoading(ResourceLoadingArgs args)
```

### Örnekler

Dış kaynakları bir belgeye yükleme işleminin nasıl özelleştirileceğini gösterir.

```csharp
{
    Document doc = new Document();
    doc.ResourceLoadingCallback = new ImageNameHandler();

    DocumentBuilder builder = new DocumentBuilder(doc);

    // Görüntüler genellikle bir URI veya bir bayt dizisi kullanılarak eklenir.
    // Bir kaynak yükünün her örneği, geri aramamızın ResourceLoading yöntemini çağıracaktır.
    builder.InsertImage("Google logo");
    builder.InsertImage("Aspose logo");
    builder.InsertImage("Watermark");

    Assert.AreEqual(3, doc.GetChildNodes(NodeType.Shape, true).Count);

    doc.Save(ArtifactsDir + "DocumentBase.ResourceLoadingCallback.docx");

/// <summary>
/// URI'lerin aksine önceden tanımlanmış kısayolları kullanarak görüntüleri bir belgeye yüklememize izin verir.
/// Bu, görüntü yükleme mantığını belge yapısının geri kalanından ayıracaktır.
/// </summary>
private class ImageNameHandler : IResourceLoadingCallback
{
    public ResourceLoadingAction ResourceLoading(ResourceLoadingArgs args)
    {
        // Bu geri arama, bir görüntü yüklerken görüntü kısayollarından biriyle karşılaşırsa,
        // tanımlı her bir kestirme yol için URI gibi davranmak yerine benzersiz bir mantık uygulayacaktır.
        if (args.ResourceType == ResourceType.Image)
            switch (args.OriginalUri)
            {
                case "Google logo":
                    using (WebClient webClient = new WebClient())
                    {
                        args.SetData(webClient.DownloadData("http://www.google.com/images/logos/ps_logo2.png"));
                    }

                    return ResourceLoadingAction.UserProvided;

                case "Aspose logo":
                    args.SetData(File.ReadAllBytes(ImageDir + "Logo.jpg"));

                    return ResourceLoadingAction.UserProvided;

                case "Watermark":
                    args.SetData(File.ReadAllBytes(ImageDir + "Transparent background logo.png"));

                    return ResourceLoadingAction.UserProvided;
            }

        return ResourceLoadingAction.Default;
    }
}
```

### Ayrıca bakınız

* enum [ResourceLoadingAction](../../resourceloadingaction/)
* class [ResourceLoadingArgs](../../resourceloadingargs/)
* interface [IResourceLoadingCallback](../)
* ad alanı [Aspose.Words.Loading](../../iresourceloadingcallback/)
* toplantı [Aspose.Words](../../../)


