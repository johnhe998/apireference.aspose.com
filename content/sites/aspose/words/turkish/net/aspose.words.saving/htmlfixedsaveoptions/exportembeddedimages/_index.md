---
title: HtmlFixedSaveOptions.ExportEmbeddedImages
second_title: Aspose.Words for .NET API Referansı
description: HtmlFixedSaveOptions mülk. Görüntülerin Html belgesine Base64 biçiminde gömülmesi gerekip gerekmediğini belirtir. Bu bayrağın ayarlanması çıktı Html dosyasının boyutunu önemli ölçüde artırabilir.
type: docs
weight: 60
url: /tr/net/aspose.words.saving/htmlfixedsaveoptions/exportembeddedimages/
---
## HtmlFixedSaveOptions.ExportEmbeddedImages property

Görüntülerin Html belgesine Base64 biçiminde gömülmesi gerekip gerekmediğini belirtir. Bu bayrağın ayarlanması, çıktı Html dosyasının boyutunu önemli ölçüde artırabilir.

```csharp
public bool ExportEmbeddedImages { get; set; }
```

### Örnekler

Bir belgeyi Html'e aktarırken görüntülerin nerede saklanacağının nasıl belirleneceğini gösterir.

```csharp
Document doc = new Document(MyDir + "Images.docx");

// Gömülü resimler içeren bir belgeyi .html'ye aktardığımızda,
// Aspose.Words görüntüleri iki olası konuma yerleştirebilir.
// "ExportEmbeddedImages" bayrağının "true" olarak ayarlanması ham verileri depolayacaktır
// çıktı HTML belgesindeki tüm resimler için, <image> etiketler.
// Bu bayrağı "false" olarak ayarlamak, her görüntü için yerel dosya sisteminde bir görüntü dosyası oluşturacaktır,
// ve tüm bu dosyaları ayrı bir klasörde saklayın.
HtmlFixedSaveOptions htmlFixedSaveOptions = new HtmlFixedSaveOptions
{
    ExportEmbeddedImages = exportImages
};

doc.Save(ArtifactsDir + "HtmlFixedSaveOptions.ExportEmbeddedImages.html", htmlFixedSaveOptions);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlFixedSaveOptions.ExportEmbeddedImages.html");

if (exportImages)
{
    Assert.False(File.Exists(ArtifactsDir + "HtmlFixedSaveOptions.ExportEmbeddedImages/image001.jpeg"));
    Assert.True(Regex.Match(outDocContents,
        "<img class=\"awimg\" style=\"left:0pt; top:0pt; width:493.1pt; height:300.55pt;\" src=\".+\" />").Success);
}
else
{
    Assert.True(File.Exists(ArtifactsDir + "HtmlFixedSaveOptions.ExportEmbeddedImages/image001.jpeg"));
    Assert.True(Regex.Match(outDocContents,
        "<img class=\"awimg\" style=\"left:0pt; top:0pt; width:493.1pt; height:300.55pt;\" " +
        "src=\"HtmlFixedSaveOptions[.]ExportEmbeddedImages/image001[.]jpeg\" />").Success);
}
```

### Ayrıca bakınız

* class [HtmlFixedSaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../htmlfixedsaveoptions/)
* toplantı [Aspose.Words](../../../)


