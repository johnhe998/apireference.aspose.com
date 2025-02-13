---
title: HtmlSaveOptions.ExportRelativeFontSize
second_title: Aspose.Words for .NET API Referansı
description: HtmlSaveOptions mülk. HTML MHTML veya EPUBa kaydederken yazı tipi boyutlarının ilgili birimlerde çıktısının alınması gerekip gerekmediğini belirtir. Varsayılanyanlış .
type: docs
weight: 240
url: /tr/net/aspose.words.saving/htmlsaveoptions/exportrelativefontsize/
---
## HtmlSaveOptions.ExportRelativeFontSize property

HTML, MHTML veya EPUB'a kaydederken yazı tipi boyutlarının ilgili birimlerde çıktısının alınması gerekip gerekmediğini belirtir. Varsayılan`yanlış` .

```csharp
public bool ExportRelativeFontSize { get; set; }
```

### Notlar

Mevcut birçok belgede (HTML, IDPF EPUB) yazı tipi boyutları göreceli birimlerde belirtilir. Bu, uygulamaların belgeleri görüntülerken/işlerken metin boyutunu ayarlamasına izin verir. Örneğin, Microsoft Internet Explorer , "Görünüm-&gt;Metin Boyutu" alt menüsüne sahiptir, Adobe Digital Editions'ın iki düğmesi vardır: Metin Boyutunu Artır/Küçült. Bu işlevin çalışmasını bekliyorsanız, ayarlayın`ExportRelativeFontSize` mülk`doğru` .

Aspose Words belge modeli yalnızca mutlak yazı tipi boyutu birimleri içerir ve bunlarla çalışır. Göreli birimlerin bazı başlangıç (standart) boyutlarından yeniden hesaplanması için ek mantığa ihtiyacı vardır. yazı tipi boyutu **Normal** belge stili standart olarak alınır. örneğin, eğer **Normal** 12pt yazı tipine sahip ve bazı metinler 18pt ise, çıktı olarak olacaktır. **1.5em.** HTML'ye.

Bu seçenek etkinleştirildiğinde, metin dışındaki belge öğelerinin yine de mutlak boyutları olacaktır. Ayrıca bazı metinle ilgili nitelikler mutlak olarak ifade edilebilir. Özellikle, "tam" kuralı ile belirtilen satır aralığı, metin ölçeklenirken istenmeyen sonuçlar üretebilir. Bu nedenle, kaynak belgeler doğru şekilde tasarlanmalı ve ile dışa aktarılırken test edilmelidir.`ExportRelativeFontSize` ayarlanır`doğru`.

### Örnekler

.html dosyasına kaydederken göreli yazı tipi boyutlarının nasıl kullanılacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Default font size, ");
builder.Font.Size = 24;
builder.Writeln("2x default font size,");
builder.Font.Size = 96;
builder.Write("8x default font size");

// Belgeyi HTML'ye kaydettiğimizde, SaveOptions nesnesini iletebiliriz
// göreli mi yoksa mutlak yazı tipi boyutlarının mı kullanılacağını belirlemek için.
// Font boyutlarını bildirmek için "ExportRelativeFontSize" bayrağını "true" olarak ayarlayın
 // mevcut yazı tipi boyutunu çarpan bir faktör olan "em" ölçü birimini kullanarak.
// Font boyutlarını bildirmek için "ExportRelativeFontSize" bayrağını "false" olarak ayarlayın
// yazı tipinin nokta cinsinden mutlak boyutu olan "pt" ölçü birimini kullanarak.
HtmlSaveOptions options = new HtmlSaveOptions { ExportRelativeFontSize = exportRelativeFontSize };

doc.Save(ArtifactsDir + "HtmlSaveOptions.RelativeFontSize.html", options);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlSaveOptions.RelativeFontSize.html");

if (exportRelativeFontSize)
{
    Assert.True(outDocContents.Contains(
        "<body style=\"font-family:'Times New Roman'\">" +
            "<div>" +
                "<p style=\"margin-top:0pt; margin-bottom:0pt\">" +
                    "<span>Default font size, </span>" +
                "</p>" +
                "<p style=\"margin-top:0pt; margin-bottom:0pt; font-size:2em\">" +
                    "<span>2x default font size,</span>" +
                "</p>" +
                "<p style=\"margin-top:0pt; margin-bottom:0pt; font-size:8em\">" +
                    "<span>8x default font size</span>" +
                "</p>" +
            "</div>" +
        "</body>"));
}
else
{
    Assert.True(outDocContents.Contains(
        "<body style=\"font-family:'Times New Roman'; font-size:12pt\">" +
            "<div>" +
                "<p style=\"margin-top:0pt; margin-bottom:0pt\">" +
                    "<span>Default font size, </span>" +
                "</p>" +
                "<p style=\"margin-top:0pt; margin-bottom:0pt; font-size:24pt\">" +
                    "<span>2x default font size,</span>" +
                "</p>" +
                "<p style=\"margin-top:0pt; margin-bottom:0pt; font-size:96pt\">" +
                    "<span>8x default font size</span>" +
                "</p>" +
            "</div>" +
        "</body>"));
}
```

### Ayrıca bakınız

* class [HtmlSaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../htmlsaveoptions/)
* toplantı [Aspose.Words](../../../)


