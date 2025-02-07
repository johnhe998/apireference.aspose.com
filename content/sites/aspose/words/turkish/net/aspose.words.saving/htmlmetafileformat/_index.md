---
title: Enum HtmlMetafileFormat
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Saving.HtmlMetafileFormat Sıralama. Meta dosyalarının HTML belgelerine kaydedildiği biçimi belirtir.
type: docs
weight: 4830
url: /tr/net/aspose.words.saving/htmlmetafileformat/
---
## HtmlMetafileFormat enumeration

Meta dosyalarının HTML belgelerine kaydedildiği biçimi belirtir.

```csharp
public enum HtmlMetafileFormat
```

### değerler

| İsim | Değer | Tanım |
| --- | --- | --- |
| Png | `0` | Meta dosyaları PNG resimlerine raster olarak işlenir. |
| Svg | `1` | Meta dosyaları, vektör SVG görüntülerine dönüştürülür. |
| EmfOrWmf | `2` | Meta dosyaları dönüştürülmeden olduğu gibi kaydedilir. |

### Örnekler

HTML belgelerini kaydederken SVG nesnelerinin nasıl farklı bir biçime dönüştürüleceğini gösterir.

```csharp
string html = 
    @"<html>
        <svg xmlns='http://www.w3.org/2000/svg' width='500' height='40' viewBox='0 0 500 40'>
            <text x='0' y='35' font-family='Verdana' font-size='35'>Hello world!</text>
        </svg>
    </html>";

// Eski davranışı geri almak için 'ConvertSvgToEmf' kullanın
// bir HTML belgesinden yüklenen tüm SVG resimlerinin EMF'ye dönüştürüldüğü yer.
// Artık SVG görüntüleri dönüştürülmeden yükleniyor
// yükleme seçeneklerinde belirtilen MS Word sürümü yerel olarak SVG görüntülerini destekliyorsa.
HtmlLoadOptions loadOptions = new HtmlLoadOptions { ConvertSvgToEmf = true };

Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);

// Bu belge bir <svg> öğe metin şeklinde.
// Belgeyi HTML'ye kaydettiğimizde, SaveOptions nesnesini iletebiliriz
// kaydetme işleminin bu nesneyi nasıl işlediğini belirlemek için.
// PNG görüntüsüne dönüştürmek için "MetafileFormat" özelliğinin "HtmlMetafileFormat.Png" olarak ayarlanması.
// "MetafileFormat" özelliğinin "HtmlMetafileFormat.Svg" olarak ayarlanması onu bir SVG nesnesi olarak korur.
// Bir meta dosyaya dönüştürmek için "MetafileFormat" özelliğinin "HtmlMetafileFormat.EmfOrWmf" olarak ayarlanması.
HtmlSaveOptions options = new HtmlSaveOptions { MetafileFormat = htmlMetafileFormat };

doc.Save(ArtifactsDir + "HtmlSaveOptions.MetafileFormat.html", options);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlSaveOptions.MetafileFormat.html");

switch (htmlMetafileFormat)
{
    case HtmlMetafileFormat.Png:
        Assert.True(outDocContents.Contains(
            "<p style=\"margin-top:0pt; margin-bottom:0pt\">" +
                "<img src=\"HtmlSaveOptions.MetafileFormat.001.png\" width=\"500\" height=\"40\" alt=\"\" " +
                "style=\"-aw-left-pos:0pt; -aw-rel-hpos:column; -aw-rel-vpos:paragraph; -aw-top-pos:0pt; -aw-wrap-type:inline\" />" +
            "</p>"));
        break;
    case HtmlMetafileFormat.Svg:
        Assert.True(outDocContents.Contains(
            "<span style=\"-aw-left-pos:0pt; -aw-rel-hpos:column; -aw-rel-vpos:paragraph; -aw-top-pos:0pt; -aw-wrap-type:inline\">" +
            "<svg xmlns=\"http://www.w3.org/2000/svg\" xmlns:xlink=\"http://www.w3.org/1999/xlink\" version=\"1.1\" width=\"499\" height= \"40\">"));
        break;
    case HtmlMetafileFormat.EmfOrWmf:
        Assert.True(outDocContents.Contains(
            "<p style=\"margin-top:0pt; margin-bottom:0pt\">" +
                "<img src=\"HtmlSaveOptions.MetafileFormat.001.emf\" width=\"500\" height=\"40\" alt=\"\" " +
                "style=\"-aw-left-pos:0pt; -aw-rel-hpos:column; -aw-rel-vpos:paragraph; -aw-top-pos:0pt; -aw-wrap-type:inline\" />" +
            "</p>"));
        break;
}
```

### Ayrıca bakınız

* ad alanı [Aspose.Words.Saving](../../aspose.words.saving/)
* toplantı [Aspose.Words](../../)


