---
title: Enum TxtExportHeadersFootersMode
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Saving.TxtExportHeadersFootersMode Sıralama. Üstbilgilerin ve altbilgilerin düz metin biçimine dışa aktarılma şeklini belirtir.
type: docs
weight: 5360
url: /tr/net/aspose.words.saving/txtexportheadersfootersmode/
---
## TxtExportHeadersFootersMode enumeration

Üstbilgilerin ve altbilgilerin düz metin biçimine dışa aktarılma şeklini belirtir.

```csharp
public enum TxtExportHeadersFootersMode
```

### değerler

| İsim | Değer | Tanım |
| --- | --- | --- |
| None | `0` | Hiçbir üst bilgi ve alt bilgi dışa aktarılmaz. |
| PrimaryOnly | `1` | Her bölümün başında ve sonunda yalnızca birincil üstbilgiler ve altbilgiler dışa aktarılır. |
| AllAtEnd | `2` | Tüm üstbilgiler ve altbilgiler, bir belgenin en sonunda tüm bölüm gövdelerinden sonra yerleştirilir. |

### Örnekler

Üstbilgilerin ve altbilgilerin düz metin biçimine nasıl dışa aktarılacağının nasıl belirleneceğini gösterir.

```csharp
Document doc = new Document();

// Belgeye çift ve birincil üstbilgi/altbilgi ekleyin.
// Birincil üstbilgi/altbilgiler, çift üstbilgileri/altbilgileri geçersiz kılar.
doc.FirstSection.HeadersFooters.Add(new HeaderFooter(doc, HeaderFooterType.HeaderEven));
doc.FirstSection.HeadersFooters[HeaderFooterType.HeaderEven].AppendParagraph("Even header");
doc.FirstSection.HeadersFooters.Add(new HeaderFooter(doc, HeaderFooterType.FooterEven));
doc.FirstSection.HeadersFooters[HeaderFooterType.FooterEven].AppendParagraph("Even footer");
doc.FirstSection.HeadersFooters.Add(new HeaderFooter(doc, HeaderFooterType.HeaderPrimary));
doc.FirstSection.HeadersFooters[HeaderFooterType.HeaderPrimary].AppendParagraph("Primary header");
doc.FirstSection.HeadersFooters.Add(new HeaderFooter(doc, HeaderFooterType.FooterPrimary));
doc.FirstSection.HeadersFooters[HeaderFooterType.FooterPrimary].AppendParagraph("Primary footer");

// Bu üstbilgileri ve altbilgileri görüntülemek için sayfaları ekleyin.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Page 1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page 2");
builder.InsertBreak(BreakType.PageBreak); 
builder.Write("Page 3");

// Belgenin "Kaydet" yöntemine aktarabileceğimiz bir "TxtSaveOptions" nesnesi oluşturun
// belgeyi düz metne kaydetme şeklimizi değiştirmek için.
TxtSaveOptions saveOptions = new TxtSaveOptions();

// "ExportHeadersFootersMode" özelliğini "TxtExportHeadersFootersMode.None" olarak ayarlayın
// üstbilgileri/altbilgileri dışa aktarmamak için.
// "ExportHeadersFootersMode" özelliğini "TxtExportHeadersFootersMode.PrimaryOnly" olarak ayarlayın
// yalnızca birincil üstbilgileri/altbilgileri dışa aktarmak için.
// "ExportHeadersFootersMode" özelliğini "TxtExportHeadersFootersMode.AllAtEnd" olarak ayarlayın
// tüm bölüm gövdeleri için tüm üstbilgileri ve altbilgileri belgenin sonuna yerleştirmek için.
saveOptions.ExportHeadersFootersMode = txtExportHeadersFootersMode;

doc.Save(ArtifactsDir + "TxtSaveOptions.ExportHeadersFooters.txt", saveOptions);

string docText = File.ReadAllText(ArtifactsDir + "TxtSaveOptions.ExportHeadersFooters.txt");

switch (txtExportHeadersFootersMode)
{
    case TxtExportHeadersFootersMode.AllAtEnd:
        Assert.AreEqual("Page 1\r\n" +
                        "Page 2\r\n" +
                        "Page 3\r\n" +
                        "Even header\r\n\r\n" +
                        "Primary header\r\n\r\n" +
                        "Even footer\r\n\r\n" +
                        "Primary footer\r\n\r\n", docText);
        break;
    case TxtExportHeadersFootersMode.PrimaryOnly:
        Assert.AreEqual("Primary header\r\n" +
                        "Page 1\r\n" +
                        "Page 2\r\n" +
                        "Page 3\r\n" +
                        "Primary footer\r\n", docText);
        break;
    case TxtExportHeadersFootersMode.None:
        Assert.AreEqual("Page 1\r\n" +
                        "Page 2\r\n" +
                        "Page 3\r\n", docText);
        break;
}
```

### Ayrıca bakınız

* ad alanı [Aspose.Words.Saving](../../aspose.words.saving/)
* toplantı [Aspose.Words](../../)


