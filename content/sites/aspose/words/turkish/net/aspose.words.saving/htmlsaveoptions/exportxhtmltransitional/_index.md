---
title: HtmlSaveOptions.ExportXhtmlTransitional
second_title: Aspose.Words for .NET API Referansı
description: HtmlSaveOptions mülk. HTMLye mi yoksa MHTMLye mi kaydedilirken DOCTYPE bildiriminin yazılacağını belirtir. Ne zamandoğru  belgeye kök öğeden önce bir DOCTYPE bildirimi yazar. Varsayılan değeryanlış. EPUB veya HTML5e kaydederken Html5  DOCTYPE bildirimi her zaman yazılır.
type: docs
weight: 290
url: /tr/net/aspose.words.saving/htmlsaveoptions/exportxhtmltransitional/
---
## HtmlSaveOptions.ExportXhtmlTransitional property

HTML'ye mi yoksa MHTML'ye mi kaydedilirken DOCTYPE bildiriminin yazılacağını belirtir. Ne zaman`doğru` , belgeye kök öğeden önce bir DOCTYPE bildirimi yazar. Varsayılan değer`yanlış`. EPUB veya HTML5'e kaydederken (Html5 ) DOCTYPE bildirimi her zaman yazılır.

```csharp
public bool ExportXhtmlTransitional { get; set; }
```

### Notlar

Aspose.Words bu ayardan bağımsız olarak her zaman iyi biçimlendirilmiş HTML yazar.

Ne zaman`doğru`, HTML çıktı belgesinin başlangıcı şöyle görünecektir:

Aspose.Words, XHTML 1.0 Transitional belirtimine, göre XHTML çıktısı almayı amaçlar, ancak çıktı her zaman DTD'ye göre doğrulanmaz. Bir Microsoft Word belgesi içindeki bazı yapıların, XHTML şemasına göre doğrulanacak bir belgeyle eşlenmesi zor veya imkansızdır. Örneğin, XHTML iç içe listelere izin vermez (UL başka bir UL öğesinin içine yerleştirilemez), ancak Microsoft Word belgesinde çok düzeyli listeler oldukça sık görülür.

```csharp
<?xml version="1.0" encoding="utf-8" standalone="no" ?>
<!DOCTYPE html 
      PUBLIC "-//W3C//DTD XHTML 1.0 Geçiş//EN"
"http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml" xml:lang="en" lang="tr">
```

### Örnekler

Belgeleri Xhtml 1.0 geçiş standardına dönüştürürken DOCTYPE başlığının nasıl görüntüleneceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Hello world!");

HtmlSaveOptions options = new HtmlSaveOptions(SaveFormat.Html)
{
    HtmlVersion = HtmlVersion.Xhtml,
    ExportXhtmlTransitional = showDoctypeDeclaration,
    PrettyFormat = true
};

doc.Save(ArtifactsDir + "HtmlSaveOptions.ExportXhtmlTransitional.html", options);

// "ExportXhtmlTransitional" bayrağını "true" olarak ayarlamışsak, belgemiz yalnızca bir DOCTYPE bildirim başlığı içerecektir.
string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlSaveOptions.ExportXhtmlTransitional.html");

if (showDoctypeDeclaration)
    Assert.True(outDocContents.Contains(
        "<?xml version=\"1.0\" encoding=\"utf-8\" standalone=\"no\"?>\r\n" +
        "<!DOCTYPE html PUBLIC \"-//W3C//DTD XHTML 1.0 Transitional//EN\" \"http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd\">\r\n" +
        "<html xmlns=\"http://www.w3.org/1999/xhtml\">");
else
    Assert.True(outDocContents.Contains("<html>"));
```

### Ayrıca bakınız

* class [HtmlSaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../htmlsaveoptions/)
* toplantı [Aspose.Words](../../../)


