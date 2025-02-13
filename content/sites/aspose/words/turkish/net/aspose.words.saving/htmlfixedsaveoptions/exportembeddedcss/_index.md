---
title: HtmlFixedSaveOptions.ExportEmbeddedCss
second_title: Aspose.Words for .NET API Referansı
description: HtmlFixedSaveOptions mülk. CSSnin Basamaklı Stil Sayfası Html belgesine gömülmesi gerekip gerekmediğini belirtir.
type: docs
weight: 40
url: /tr/net/aspose.words.saving/htmlfixedsaveoptions/exportembeddedcss/
---
## HtmlFixedSaveOptions.ExportEmbeddedCss property

CSS'nin (Basamaklı Stil Sayfası) Html belgesine gömülmesi gerekip gerekmediğini belirtir.

```csharp
public bool ExportEmbeddedCss { get; set; }
```

### Örnekler

Bir belgeyi Html'e aktarırken CSS stil sayfalarının nerede saklanacağının nasıl belirleneceğini gösterir.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// Bir belgeyi html'ye aktardığımızda, Aspose.Words ayrıca belgeyi biçimlendirmek için bir CSS stil sayfası oluşturacaktır.
// "ExportEmbeddedCss" bayrağını "true" olarak ayarlayarak CSS stil sayfasını bir .css dosyasına kaydedin,
// ve bir <link> kullanarak html belgesindeki dosyaya bağlantı verin. öğe.
// Bayrağı "false" olarak ayarlamak CSS stil sayfasını Html belgesine gömer,
// iki yerine yalnızca bir dosya oluşturacak.
HtmlFixedSaveOptions htmlFixedSaveOptions = new HtmlFixedSaveOptions
{
    ExportEmbeddedCss = exportEmbeddedCss
};

doc.Save(ArtifactsDir + "HtmlFixedSaveOptions.ExportEmbeddedCss.html", htmlFixedSaveOptions);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlFixedSaveOptions.ExportEmbeddedCss.html");

if (exportEmbeddedCss)
{
    Assert.True(Regex.Match(outDocContents, "<style type=\"text/css\">").Success);
    Assert.False(File.Exists(ArtifactsDir + "HtmlFixedSaveOptions.ExportEmbeddedCss/styles.css"));
}
else
{
    Assert.True(Regex.Match(outDocContents,
        "<link rel=\"stylesheet\" type=\"text/css\" href=\"HtmlFixedSaveOptions[.]ExportEmbeddedCss/styles[.]css\" media=\"all\" />").Success);
    Assert.True(File.Exists(ArtifactsDir + "HtmlFixedSaveOptions.ExportEmbeddedCss/styles.css"));
}
```

### Ayrıca bakınız

* class [HtmlFixedSaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../htmlfixedsaveoptions/)
* toplantı [Aspose.Words](../../../)


