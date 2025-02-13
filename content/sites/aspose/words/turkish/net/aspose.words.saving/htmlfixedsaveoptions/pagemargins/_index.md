---
title: HtmlFixedSaveOptions.PageMargins
second_title: Aspose.Words for .NET API Referansı
description: HtmlFixedSaveOptions mülk. Bir HTML belgesindeki sayfaların etrafındaki kenar boşluklarını belirtir. Kenar boşlukları değeri puan olarak ölçülür ve 0a eşit veya 0dan büyük olmalıdır. Varsayılan değer 10 puandır.
type: docs
weight: 120
url: /tr/net/aspose.words.saving/htmlfixedsaveoptions/pagemargins/
---
## HtmlFixedSaveOptions.PageMargins property

Bir HTML belgesindeki sayfaların etrafındaki kenar boşluklarını belirtir. Kenar boşlukları değeri puan olarak ölçülür ve 0'a eşit veya 0'dan büyük olmalıdır. Varsayılan değer 10 puandır.

```csharp
public double PageMargins { get; set; }
```

### Notlar

değerine bağlıdır[`PageHorizontalAlignment`](../pagehorizontalalignment/) Emlak:

* Değer şuysa, üst, alt ve sol sayfa kenar boşluklarını tanımlar.Left .
* Değer şuysa, üst, alt ve sağ sayfa kenar boşluklarını tanımlar.Right .
* Değer şuysa, sayfanın üst ve alt kenar boşluklarını tanımlar.Center .

### Örnekler

Bir belgeyi HTML'ye kaydederken sayfa kenar boşluklarının nasıl ayarlanacağını gösterir.

```csharp
Document doc = new Document(MyDir + "Document.docx");

HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions
{
    PageMargins = 15
};

doc.Save(ArtifactsDir + "HtmlFixedSaveOptions.PageMargins.html", saveOptions);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlFixedSaveOptions.PageMargins/styles.css");

Assert.True(Regex.Match(outDocContents,
    "[.]awpage { position:relative; border:solid 1pt black; margin:15pt auto 15pt auto; overflow:hidden; }").Success);
```

### Ayrıca bakınız

* class [HtmlFixedSaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../htmlfixedsaveoptions/)
* toplantı [Aspose.Words](../../../)


