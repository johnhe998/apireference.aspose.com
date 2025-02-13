---
title: HtmlSaveOptions.ImagesFolderAlias
second_title: Aspose.Words for .NET API Referansı
description: HtmlSaveOptions mülk. Bir HTML belgesine yazılan görüntü URIlerini oluşturmak için kullanılan klasörün adını belirtir. Varsayılan boş bir dizedir.
type: docs
weight: 380
url: /tr/net/aspose.words.saving/htmlsaveoptions/imagesfolderalias/
---
## HtmlSaveOptions.ImagesFolderAlias property

Bir HTML belgesine yazılan görüntü URI'lerini oluşturmak için kullanılan klasörün adını belirtir. Varsayılan boş bir dizedir.

```csharp
public string ImagesFolderAlias { get; set; }
```

### Notlar

Bir kaydettiğinizde[`Document`](../../../aspose.words/document/) Aspose.Words'ün, HTML formatında, belgeye gömülü tüm resimleri bağımsız dosyalar olarak kaydetmesi gerekir.[`ImagesFolder`](../imagesfolder/) , görüntülerin nereye kaydedileceğini belirlemenize ve`ImagesFolderAlias` , görüntü URI'lerinin nasıl oluşturulacağını belirlemeye izin verir.

Eğer`ImagesFolderAlias`boş bir dize değilse, HTML'ye yazılan görüntü URI'siImagesFolderAlias + &lt;görüntü dosyası adı&gt;.

Eğer`ImagesFolderAlias` boş bir dize ise, HTML'ye yazılmış resim URI'siImagesFolder + &lt;görüntü dosyası adı&gt;.

Eğer`ImagesFolderAlias` ayarlandı '.' (nokta), daha sonra resim dosyası adı, diğer seçeneklerden bağımsız olarak yol olmadan HTML'ye yazılacaktır.

URIs görüntüsünü oluşturmak için klasörün adını belirtmenin alternatif yolu kullanmaktır.[`ResourceFolderAlias`](../resourcefolderalias/).

### Örnekler

Aspose.Words'ün bir belgeyi HTML'ye kaydederken oluşturacağı harici olarak kaydedilmiş kaynaklar için klasörlerin ve klasör takma adlarının nasıl ayarlanacağını gösterir.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

HtmlSaveOptions options = new HtmlSaveOptions
{
    CssStyleSheetType = CssStyleSheetType.External,
    ExportFontResources = true,
    ImageResolution = 72,
    FontResourcesSubsettingSizeThreshold = 0,
    FontsFolder = ArtifactsDir + "Fonts",
    ImagesFolder = ArtifactsDir + "Images",
    ResourceFolder = ArtifactsDir + "Resources",
    FontsFolderAlias = "http://example.com/fonts",
    ImagesFolderAlias = "http://example.com/images",
    ResourceFolderAlias = "http://example.com/resources",
    ExportOriginalUrlForLinkedImages = true
};

doc.Save(ArtifactsDir + "HtmlSaveOptions.FolderAlias.html", options);
```

### Ayrıca bakınız

* class [HtmlSaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../htmlsaveoptions/)
* toplantı [Aspose.Words](../../../)


