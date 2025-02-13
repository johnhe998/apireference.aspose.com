---
title: HtmlSaveOptions.ExportLanguageInformation
second_title: Aspose.Words for .NET API Referansı
description: HtmlSaveOptions mülk. Dil bilgilerinin HTML MHTML veya EPUBa aktarılıp aktarılmayacağını belirtir. Varsayılanyanlış .
type: docs
weight: 190
url: /tr/net/aspose.words.saving/htmlsaveoptions/exportlanguageinformation/
---
## HtmlSaveOptions.ExportLanguageInformation property

Dil bilgilerinin HTML, MHTML veya EPUB'a aktarılıp aktarılmayacağını belirtir. Varsayılan`yanlış` .

```csharp
public bool ExportLanguageInformation { get; set; }
```

### Notlar

Bu özellik olarak ayarlandığında`doğru` Aspose.Words çıktıları **dil** Dili belirten document öğelerindeki HTML özelliği. Bu, dille ilgili anlambilimi korumak için gerekli olabilir.

### Örnekler

.html dosyasına kaydederken dil bilgilerinin nasıl korunacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Metni farklı yerel ayarlarda biçimlendirirken yazmak için oluşturucuyu kullanın.
builder.Font.LocaleId = new CultureInfo("en-US").LCID;
builder.Writeln("Hello world!");

builder.Font.LocaleId = new CultureInfo("en-GB").LCID;
builder.Writeln("Hello again!");

builder.Font.LocaleId = new CultureInfo("ru-RU").LCID;
builder.Write("Привет, мир!");

// Belgeyi HTML'ye kaydederken SaveOptions nesnesini iletebiliriz
// biçimlendirilmiş her metnin yerel ayarını korumak veya atmak için.
// "ExportLanguageInformation" bayrağını "true" olarak ayarlarsak,
// çıktı HTML belgesi, <span> etiketler.
// "ExportLanguageInformation" bayrağını "false" olarak ayarlarsak,
// çıktı HTML belgesindeki metin herhangi bir yerel ayar bilgisi içermeyecektir.
HtmlSaveOptions options = new HtmlSaveOptions
{
    ExportLanguageInformation = exportLanguageInformation,
    PrettyFormat = true
};

doc.Save(ArtifactsDir + "HtmlSaveOptions.ExportLanguageInformation.html", options);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlSaveOptions.ExportLanguageInformation.html");

if (exportLanguageInformation)
{
    Assert.True(outDocContents.Contains("<span>Hello world!</span>"));
    Assert.True(outDocContents.Contains("<span lang=\"en-GB\">Hello again!</span>"));
    Assert.True(outDocContents.Contains("<span lang=\"ru-RU\">Привет, мир!</span>"));
}
else
{
    Assert.True(outDocContents.Contains("<span>Hello world!</span>"));
    Assert.True(outDocContents.Contains("<span>Hello again!</span>"));
    Assert.True(outDocContents.Contains("<span>Привет, мир!</span>"));
}
```

### Ayrıca bakınız

* class [HtmlSaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../htmlsaveoptions/)
* toplantı [Aspose.Words](../../../)


