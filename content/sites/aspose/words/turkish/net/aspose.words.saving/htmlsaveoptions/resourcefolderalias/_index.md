---
title: HtmlSaveOptions.ResourceFolderAlias
second_title: Aspose.Words for .NET API Referansı
description: HtmlSaveOptions mülk. Bir HTML belgesine yazılan tüm kaynakların URIlerini oluşturmak için kullanılan klasörün adını belirtir. Varsayılan boş bir dizedir.
type: docs
weight: 430
url: /tr/net/aspose.words.saving/htmlsaveoptions/resourcefolderalias/
---
## HtmlSaveOptions.ResourceFolderAlias property

Bir HTML belgesine yazılan tüm kaynakların URI'lerini oluşturmak için kullanılan klasörün adını belirtir. Varsayılan boş bir dizedir.

```csharp
public string ResourceFolderAlias { get; set; }
```

### Notlar

`ResourceFolderAlias` tüm kaynak dosyaları için URI'lerin nasıl oluşturulması gerektiğini belirtmenin en basit yoludur. Görüntüler ve yazı tipleri için aynı bilgiler ayrı ayrı belirtilebilir.[`ImagesFolderAlias`](../imagesfolderalias/) ve[`FontsFolderAlias`](../fontsfolderalias/) özellikleri sırasıyla. Ancak, CSS. için ayrı bir özellik yoktur.

`ResourceFolderAlias` daha düşük önceliğe sahiptir[`FontsFolderAlias`](../fontsfolderalias/) ve[`ImagesFolderAlias`](../imagesfolderalias/) . Örneğin, eğer her ikisi de`ResourceFolderAlias` ve[`FontsFolderAlias`](../fontsfolderalias/) belirtilirse, yazı tiplerinin URI'leri kullanılarak oluşturulacaktır.[`FontsFolderAlias`](../fontsfolderalias/) , görüntülerin ve CSS'nin URI'leri kullanılarak oluşturulacaktır.`ResourceFolderAlias`.

Eğer`ResourceFolderAlias` boş,[`ResourceFolder`](../resourcefolder/)özellik değeri, kaynak URI'leri oluşturmak için kullanılacak .

Eğer`ResourceFolderAlias` ayarlandı '.' (nokta), kaynak URI'leri, herhangi bir yol olmadan yalnızca dosya adlarını içerecektir.

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


