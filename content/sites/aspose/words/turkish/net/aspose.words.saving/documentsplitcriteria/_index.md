---
title: Enum DocumentSplitCriteria
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Saving.DocumentSplitCriteria Sıralama. Kaydederken belgenin parçalara nasıl bölüneceğini belirtir.Html veyaEpub biçim.
type: docs
weight: 4700
url: /tr/net/aspose.words.saving/documentsplitcriteria/
---
## DocumentSplitCriteria enumeration

Kaydederken belgenin parçalara nasıl bölüneceğini belirtir.Html veyaEpub biçim.

```csharp
[Flags]
public enum DocumentSplitCriteria
```

### değerler

| İsim | Değer | Tanım |
| --- | --- | --- |
| None | `0` | Belge bölünmemiş. |
| PageBreak | `1` | Belge, açık sayfa sonlarında bölümlere ayrılır. Bir sayfa sonu, bir[`PageBreak`](../../aspose.words/controlchar/pagebreak/) karakter, yeni bir sayfada yeni bölümün başlangıcını belirten bir bölüm sonu, veya[`PageBreakBefore`](../../aspose.words/paragraphformat/pagebreakbefore/) özellik olarak ayarlandı`doğru` . |
| ColumnBreak | `2` | Belge, sütun sonlarında bölümlere ayrılır. Bir sütun sonu, bir[`ColumnBreak`](../../aspose.words/controlchar/columnbreak/) karakter veya yeni bir sütunda yeni bölümün başlangıcını belirten bir bölüm sonu. |
| SectionBreak | `4` | Belge, herhangi bir türdeki bir bölüm sonunda parçalara bölünür. |
| HeadingParagraph | `8` | Belge, başlık stili kullanılarak biçimlendirilmiş bir paragrafta bölümlere ayrılır **Başlık 1** , **Başlık 2** vb. İle birlikte kullanın[`DocumentSplitHeadingLevel`](../htmlsaveoptions/documentsplitheadinglevel/) bölüneceği (1'den belirtilen düzeye kadar) başlık düzeylerini belirtmek için. |

### Notlar

`DocumentSplitCriteria`birleştirilebilen bir bayrak kümesidir. Örneğin, aynı dışa aktarma işleminde belge 'yi sayfa sonlarında ve başlık paragraflarında bölebilirsiniz.

Farklı kriterler kısmen örtüşebilir. Örneğin, **Başlık 1** stil sıklıkla verilir [`PageBreakBefore`](../../aspose.words/paragraphformat/pagebreakbefore/) mülk, bu nedenle iki kritere girer:PageBreak ve HeadingParagraph. Bazı bölüm sonları sayfa sonlarına vb. neden olabilir. Tipik durumlarda yalnızca bir bayrak belirtmek en pratik seçenektir.

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

* ad alanı [Aspose.Words.Saving](../../aspose.words.saving/)
* toplantı [Aspose.Words](../../)


