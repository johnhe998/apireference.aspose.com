---
title: HtmlSaveOptions.FontsFolderAlias
second_title: Aspose.Words for .NET API Referansı
description: HtmlSaveOptions mülk. Bir HTML belgesine yazılan yazı tipi URIlerini oluşturmak için kullanılan klasörün adını belirtir. Varsayılan boş bir dizedir.
type: docs
weight: 330
url: /tr/net/aspose.words.saving/htmlsaveoptions/fontsfolderalias/
---
## HtmlSaveOptions.FontsFolderAlias property

Bir HTML belgesine yazılan yazı tipi URI'lerini oluşturmak için kullanılan klasörün adını belirtir. Varsayılan boş bir dizedir.

```csharp
public string FontsFolderAlias { get; set; }
```

### Notlar

Bir kaydettiğinizde[`Document`](../../../aspose.words/document/) HTML formatında ve[`ExportFontResources`](../exportfontresources/) olarak ayarlandı`doğru` , Aspose.Words'ün belgede kullanılan yazı tiplerini bağımsız dosyalar olarak kaydetmesi gerekir. [`FontsFolder`](../fontsfolder/) yazı tiplerinin nereye kaydedileceğini belirlemenize ve `FontsFolderAlias` yazı tipi URI'lerinin nasıl oluşturulacağını belirlemeye izin verir.

Eğer`FontsFolderAlias` boş bir dize değilse, HTML'ye yazılan yazı tipi URI'siFontsFolderAlias + &lt;font dosya adı&gt;.

Eğer`FontsFolderAlias` boş bir dize ise, HTML'ye yazılan yazı tipi URI'siFontsFolder + &lt;font dosya adı&gt;.

Eğer`FontsFolderAlias`ayarlandı '.' (nokta), daha sonra yazı tipi dosya adı, diğer seçeneklerden bağımsız olarak yol olmadan HTML'ye yazılacaktır.

URIs yazı tipini oluşturacak klasörün adını belirtmenin alternatif yolu kullanmaktır.[`ResourceFolderAlias`](../resourcefolderalias/).

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


