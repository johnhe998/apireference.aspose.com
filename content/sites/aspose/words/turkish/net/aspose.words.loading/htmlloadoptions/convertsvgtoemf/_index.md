---
title: HtmlLoadOptions.ConvertSvgToEmf
second_title: Aspose.Words for .NET API Referansı
description: HtmlLoadOptions mülk. Yüklenen SVG görüntülerinin EMF biçimine dönüştürülüp dönüştürülmeyeceğini belirten bir değer alır veya ayarlar. Varsayılan değeryanlış ve mümkünse yüklenen SVG görüntüleri dönüştürülmeden olduğu gibi saklanır.
type: docs
weight: 30
url: /tr/net/aspose.words.loading/htmlloadoptions/convertsvgtoemf/
---
## HtmlLoadOptions.ConvertSvgToEmf property

Yüklenen SVG görüntülerinin EMF biçimine dönüştürülüp dönüştürülmeyeceğini belirten bir değer alır veya ayarlar. Varsayılan değer`yanlış` ve mümkünse, yüklenen SVG görüntüleri dönüştürülmeden olduğu gibi saklanır.

```csharp
public bool ConvertSvgToEmf { get; set; }
```

### Notlar

MS Word'ün daha yeni sürümleri, yerel olarak SVG görüntülerini destekler. Yükleme seçeneklerinde belirtilen MS Word sürümü SVG'yi destekliyorsa, Aspose.Words, SVG görüntülerini dönüştürmeden olduğu gibi depolayacaktır. SVG desteklenmiyorsa, yüklenen SVG görüntüleri EMF biçimine dönüştürülür.

Ancak, bu seçenek olarak ayarlanırsa`doğru` , Aspose.Words, SVG görüntüleri MS Word'ün belirtilen sürümü tarafından desteklense bile, yüklenen SVG görüntülerini EMF'ye dönüştürecektir.

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

* class [HtmlLoadOptions](../)
* ad alanı [Aspose.Words.Loading](../../htmlloadoptions/)
* toplantı [Aspose.Words](../../../)


