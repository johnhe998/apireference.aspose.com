---
title: Enum ExportHeadersFootersMode
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Saving.ExportHeadersFootersMode Sıralama. Üstbilgilerin ve altbilgilerin HTML MHTML veya EPUBa nasıl aktarılacağını belirtir.
type: docs
weight: 4740
url: /tr/net/aspose.words.saving/exportheadersfootersmode/
---
## ExportHeadersFootersMode enumeration

Üstbilgilerin ve altbilgilerin HTML, MHTML veya EPUB'a nasıl aktarılacağını belirtir.

```csharp
public enum ExportHeadersFootersMode
```

### değerler

| İsim | Değer | Tanım |
| --- | --- | --- |
| None | `0` | Üstbilgiler ve altbilgiler dışa aktarılmaz. |
| PerSection | `1` | Birincil üstbilgiler ve altbilgiler, her bölümün başında ve sonunda dışa aktarılır. |
| FirstSectionHeaderLastSectionFooter | `2` | İlk bölümün birincil başlığı, belgenin başında dışa aktarılır ve birincil alt bilgi, sonundadır. |
| FirstPageHeaderFooterPerSection | `3` | İlk sayfa üstbilgisi ve altbilgisi, her bölümün başında ve sonunda dışa aktarılır. |

### Örnekler

Bir belgeyi HTML'ye kaydederken üstbilgilerin/altbilgilerin nasıl atlanacağını gösterir.

```csharp
Document doc = new Document(MyDir + "Header and footer types.docx");

// Bu belge üstbilgi ve altbilgi içerir. Onlara "HeadersFooters" koleksiyonu aracılığıyla erişebiliriz.
Assert.AreEqual("First header", doc.FirstSection.HeadersFooters[HeaderFooterType.HeaderFirst].GetText().Trim());

// .html gibi biçimler belgeyi sayfalara bölmez, bu nedenle üstbilgiler/altbilgiler aynı şekilde çalışmaz
// Microsoft Word kullanarak belgeyi .docx olarak açtığımızda yaparlar.
// Üstbilgileri/altbilgileri olan bir belgeyi html'ye dönüştürürsek, dönüştürme, üstbilgileri/altbilgileri gövde metnine dönüştürür.
// Html'ye dönüştürürken üstbilgileri/altbilgileri atlamak için SaveOptions nesnesini kullanabiliriz.
HtmlSaveOptions saveOptions =
    new HtmlSaveOptions(SaveFormat.Html) { ExportHeadersFootersMode = ExportHeadersFootersMode.None };

doc.Save(ArtifactsDir + "HeaderFooter.ExportMode.html", saveOptions);

// Kaydedilmiş belgemizi açın ve başlığın metnini içermediğini doğrulayın
doc = new Document(ArtifactsDir + "HeaderFooter.ExportMode.html");

Assert.IsFalse(doc.Range.Text.Contains("First header"));
```

### Ayrıca bakınız

* property [ExportHeadersFootersMode](../htmlsaveoptions/exportheadersfootersmode/)
* ad alanı [Aspose.Words.Saving](../../aspose.words.saving/)
* toplantı [Aspose.Words](../../)


