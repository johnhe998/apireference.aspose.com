---
title: HtmlSaveOptions.HtmlSaveOptions
second_title: Aspose.Words for .NET API Referansı
description: HtmlSaveOptions inşaatçı. Bu sınıfın bir document dosyasını şuraya kaydetmek için kullanılabilecek yeni bir örneğini başlatır.Html biçim.
type: docs
weight: 10
url: /tr/net/aspose.words.saving/htmlsaveoptions/htmlsaveoptions/
---
## HtmlSaveOptions() {#constructor}

Bu sınıfın, bir document dosyasını şuraya kaydetmek için kullanılabilecek yeni bir örneğini başlatır.Html biçim.

```csharp
public HtmlSaveOptions()
```

### Örnekler

Bir belgeyi .epub'a kaydederken belirli bir kodlamanın nasıl kullanılacağını gösterir.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// Kaydeteceğimiz bir belgenin kodlamasını belirtmek için SaveOptions nesnesini kullanın.
HtmlSaveOptions saveOptions = new HtmlSaveOptions();
saveOptions.SaveFormat = SaveFormat.Epub;
saveOptions.Encoding = Encoding.UTF8;

// Varsayılan olarak, bir çıktı .epub belgesinin tüm içeriği tek bir HTML bölümünde olacaktır.
// Bölme kriteri, belgeyi birkaç HTML parçasına ayırmamızı sağlar.
// Belgeyi başlık paragraflarına bölmek için kriterleri belirleyeceğiz.
// Bu, belirli bir boyuttan daha önemli HTML dosyalarını okuyamayan okuyucular için kullanışlıdır.
saveOptions.DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph;

// Belge özelliklerini dışa aktarmak istediğimizi belirtin.
saveOptions.ExportDocumentProperties = true;

doc.Save(ArtifactsDir + "HtmlSaveOptions.Doc2EpubSaveOptions.epub", saveOptions);
```

### Ayrıca bakınız

* class [HtmlSaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../htmlsaveoptions/)
* toplantı [Aspose.Words](../../../)

---

## HtmlSaveOptions(SaveFormat) {#constructor_1}

Bu sınıfın, bir document dosyasını şuraya kaydetmek için kullanılabilecek yeni bir örneğini başlatır.Html ,Mhtml veyaEpub biçim.

```csharp
public HtmlSaveOptions(SaveFormat saveFormat)
```

| Parametre | Tip | Tanım |
| --- | --- | --- |
| saveFormat | SaveFormat | OlabilirHtml ,Mhtml veyaEpub. |

### Örnekler

Bir belgenin belirli bir HTML sürümüne nasıl kaydedileceğini gösterir.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

HtmlSaveOptions options = new HtmlSaveOptions(SaveFormat.Html)
{
    HtmlVersion = htmlVersion,
    PrettyFormat = true
};

doc.Save(ArtifactsDir + "HtmlSaveOptions.HtmlVersions.html", options);

// HTML belgelerimiz, farklı HTML sürümleriyle uyumlu olması için küçük farklılıklara sahip olacaktır.
string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlSaveOptions.HtmlVersions.html");

switch (htmlVersion)
{
    case HtmlVersion.Html5:
        Assert.True(outDocContents.Contains("<a id=\"_Toc76372689\"></a>"));
        Assert.True(outDocContents.Contains("<a id=\"_Toc76372689\"></a>"));
        Assert.True(outDocContents.Contains("<table style=\"-aw-border-insideh:0.5pt single #000000; -aw-border-insidev:0.5pt single #000000; border-collapse:collapse\">"));
        break;
    case HtmlVersion.Xhtml:
        Assert.True(outDocContents.Contains("<a name=\"_Toc76372689\"></a>"));
        Assert.True(outDocContents.Contains("<ul type=\"disc\" style=\"margin:0pt; padding-left:0pt\">"));
        Assert.True(outDocContents.Contains("<table cellspacing=\"0\" cellpadding=\"0\" style=\"-aw-border-insideh:0.5pt single #000000; -aw-border-insidev:0.5pt single #000000; border-collapse:collapse\""));
        break;
}
```

### Ayrıca bakınız

* enum [SaveFormat](../../../aspose.words/saveformat/)
* class [HtmlSaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../htmlsaveoptions/)
* toplantı [Aspose.Words](../../../)


