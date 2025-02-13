---
title: HtmlLoadOptions.IgnoreNoscriptElements
second_title: Aspose.Words for .NET API Referansı
description: HtmlLoadOptions mülk. noscript HTML öğelerinin göz ardı edilip edilmeyeceğini belirten bir değer alır veya ayarlar. Varsayılan değeryanlış .
type: docs
weight: 40
url: /tr/net/aspose.words.loading/htmlloadoptions/ignorenoscriptelements/
---
## HtmlLoadOptions.IgnoreNoscriptElements property

&lt;noscript&gt; HTML öğelerinin göz ardı edilip edilmeyeceğini belirten bir değer alır veya ayarlar. Varsayılan değer`yanlış` .

```csharp
public bool IgnoreNoscriptElements { get; set; }
```

### Notlar

MS Word gibi Aspose.Words de komut dosyalarını desteklemez ve varsayılan olarak &lt;noscript&gt; element içeriğini ortaya çıkan belgeye yükler. Ancak çoğu tarayıcıda komut dosyaları desteklenir ve &lt;noscript&gt; içeriği görünmez. Bu özelliğin ayarlanması`doğru` Aspose.Words'ü tüm &lt;noscript&gt; element yok saymaya zorlar ve tarayıcılarda görülene daha yakın görünen belgeler üretmeye yardımcı olur.

### Örnekler

&lt;noscript&gt; HTML öğelerinin nasıl yok sayılacağını gösterir.

```csharp
const string html = @"
    <html>
      <head>
        <title>NOSCRIPT</title>
          <meta http-equiv=""Content-Type"" content=""text/html; charset=utf-8"">
          <script type=""text/javascript"">
            alert(""Hello, world!"");
          </script>
      </head>
    <body>
      <noscript><p>Your browser does not support JavaScript!</p></noscript>
    </body>
    </html>";

HtmlLoadOptions htmlLoadOptions = new HtmlLoadOptions();
htmlLoadOptions.IgnoreNoscriptElements = ignoreNoscriptElements;

Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), htmlLoadOptions);
doc.Save(ArtifactsDir + "HtmlLoadOptions.IgnoreNoscriptElements.pdf");
```

### Ayrıca bakınız

* class [HtmlLoadOptions](../)
* ad alanı [Aspose.Words.Loading](../../htmlloadoptions/)
* toplantı [Aspose.Words](../../../)


