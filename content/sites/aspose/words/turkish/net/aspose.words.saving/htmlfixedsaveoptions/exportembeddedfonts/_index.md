---
title: HtmlFixedSaveOptions.ExportEmbeddedFonts
second_title: Aspose.Words for .NET API Referansı
description: HtmlFixedSaveOptions mülk. Yazı tiplerinin Html belgesine Base64 biçiminde gömülmesi gerekip gerekmediğini belirtir. Bu bayrağın ayarlanması çıktı Html dosyasının boyutunu önemli ölçüde artırabilir.
type: docs
weight: 50
url: /tr/net/aspose.words.saving/htmlfixedsaveoptions/exportembeddedfonts/
---
## HtmlFixedSaveOptions.ExportEmbeddedFonts property

Yazı tiplerinin Html belgesine Base64 biçiminde gömülmesi gerekip gerekmediğini belirtir. Bu bayrağın ayarlanması, çıktı Html dosyasının boyutunu önemli ölçüde artırabilir.

```csharp
public bool ExportEmbeddedFonts { get; set; }
```

### Örnekler

Bir belgeyi Html'e aktarırken gömülü yazı tiplerinin nerede saklanacağının nasıl belirleneceğini gösterir.

```csharp
Document doc = new Document(MyDir + "Embedded font.docx");

// Gömülü yazı tiplerine sahip bir belgeyi .html'ye aktardığımızda,
// Aspose.Words yazı tiplerini iki olası konuma yerleştirebilir.
// "ExportEmbeddedFonts" bayrağının "true" olarak ayarlanması, gömülü yazı tiplerinin ham verilerini CSS stil sayfasında depolayacaktır,
// "@font-face" kuralının "url" özelliğinde. Bu, büyük bir CSS stil sayfası dosyası oluşturabilir
// ve bu HTML dönüşümünün oluşturacağı harici dosya sayısını azaltın.
// Bu bayrağı "false" olarak ayarlamak, her yazı tipi için bir dosya oluşturacaktır.
// CSS stil sayfası, "@font-face" kuralının "url" özelliğini kullanarak her bir yazı tipi dosyasına bağlanacaktır.
HtmlFixedSaveOptions htmlFixedSaveOptions = new HtmlFixedSaveOptions
{
    ExportEmbeddedFonts = exportEmbeddedFonts
};

doc.Save(ArtifactsDir + "HtmlFixedSaveOptions.ExportEmbeddedFonts.html", htmlFixedSaveOptions);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlFixedSaveOptions.ExportEmbeddedFonts/styles.css");

if (exportEmbeddedFonts)
{
    Assert.True(Regex.Match(outDocContents,
        "@font-face { font-family:'Arial'; font-style:normal; font-weight:normal; src:local[(]'☺'[)], url[(].+[)] format[(]'woff'[)]; }").Success);
    Assert.AreEqual(0, Directory.GetFiles(ArtifactsDir + "HtmlFixedSaveOptions.ExportEmbeddedFonts").Count(f => f.EndsWith(".woff")));
}
else
{
    Assert.True(Regex.Match(outDocContents,
        "@font-face { font-family:'Arial'; font-style:normal; font-weight:normal; src:local[(]'☺'[)], url[(]'font001[.]woff'[)] format[(]'woff'[)]; }").Success);
    Assert.AreEqual(2, Directory.GetFiles(ArtifactsDir + "HtmlFixedSaveOptions.ExportEmbeddedFonts").Count(f => f.EndsWith(".woff")));
}
```

### Ayrıca bakınız

* class [HtmlFixedSaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../htmlfixedsaveoptions/)
* toplantı [Aspose.Words](../../../)


