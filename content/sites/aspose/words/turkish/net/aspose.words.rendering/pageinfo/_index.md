---
title: Class PageInfo
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Rendering.PageInfo sınıf. Belirli bir belge sayfası hakkındaki bilgileri temsil eder.
type: docs
weight: 4310
url: /tr/net/aspose.words.rendering/pageinfo/
---
## PageInfo class

Belirli bir belge sayfası hakkındaki bilgileri temsil eder.

```csharp
public class PageInfo
```

## Özellikleri

| İsim | Tanım |
| --- | --- |
| [HeightInPoints](../../aspose.words.rendering/pageinfo/heightinpoints/) { get; } | Sayfanın yüksekliğini nokta olarak alır. |
| [Landscape](../../aspose.words.rendering/pageinfo/landscape/) { get; } | Bu sayfa için belgede belirtilen sayfa yönü yatay ise true değerini döndürür. |
| [PaperSize](../../aspose.words.rendering/pageinfo/papersize/) { get; } | Kağıt boyutunu numaralandırma olarak alır. |
| [PaperTray](../../aspose.words.rendering/pageinfo/papertray/) { get; } | Belgede belirtildiği gibi bu sayfa için kağıt tepsisini (bölmesi) alır. Değer uygulamaya (yazıcıya) özeldir. |
| [SizeInPoints](../../aspose.words.rendering/pageinfo/sizeinpoints/) { get; } | Sayfa boyutunu punto olarak alır. |
| [WidthInPoints](../../aspose.words.rendering/pageinfo/widthinpoints/) { get; } | Sayfanın genişliğini nokta olarak alır. |

## yöntemler

| İsim | Tanım |
| --- | --- |
| [GetDotNetPaperSize](../../aspose.words.rendering/pageinfo/getdotnetpapersize/)(PaperSizeCollection) | PaperSize bununla temsil edilen sayfayı yazdırmak için uygun nesne `PageInfo` . |
| [GetSizeInPixels](../../aspose.words.rendering/pageinfo/getsizeinpixels/#getsizeinpixels)(float, float) | Belirtilen yakınlaştırma faktörü ve çözünürlük için sayfa boyutunu piksel cinsinden hesaplar. |
| [GetSizeInPixels](../../aspose.words.rendering/pageinfo/getsizeinpixels/#getsizeinpixels_1)(float, float, float) | Belirtilen yakınlaştırma faktörü ve çözünürlük için sayfa boyutunu piksel cinsinden hesaplar. |
| [GetSpecifiedPrinterPaperSource](../../aspose.words.rendering/pageinfo/getspecifiedprinterpapersource/)(PaperSourceCollection, PaperSource) | PaperSource bununla temsil edilen sayfayı yazdırmak için uygun nesne `PageInfo` . |

### Notlar

Bu nesne tarafından döndürülen sayfa genişliği ve yüksekliği, sayfanın "son" boyutunu temsil eder, örneğin, bunlar zaten doğru yöne döndürülmüşlerdir .

### Örnekler

Word belgesindeki her sayfa için sayfa boyutu ve yönlendirme bilgilerinin nasıl yazdırılacağını gösterir.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// İlk bölüm 2 sayfadır. Her birine farklı bir yazıcı kağıt tepsisi atayacağız,
// numarası bir tür kağıt kaynağıyla eşleşecek. Bu kaynaklar ve Çeşitleri değişiklik gösterecektir.
// yüklü yazıcı sürücüsüne bağlı olarak.
PrinterSettings.PaperSourceCollection paperSources = new PrinterSettings().PaperSources;

doc.FirstSection.PageSetup.FirstPageTray = paperSources[0].RawKind;
doc.FirstSection.PageSetup.OtherPagesTray = paperSources[1].RawKind;

Console.WriteLine("Document \"{0}\" contains {1} pages.", doc.OriginalFileName, doc.PageCount);

float scale = 1.0f;
float dpi = 96;

for (int i = 0; i < doc.PageCount; i++)
{
    // Her sayfa, indeksi ilgili sayfanın numarası olan bir PageInfo nesnesine sahiptir.
    PageInfo pageInfo = doc.GetPageInfo(i);

    // Sayfanın yönünü ve boyutlarını yazdırın.
    Console.WriteLine($"Page {i + 1}:");
    Console.WriteLine($"\tOrientation:\t{(pageInfo.Landscape ? "Landscape" : "Portrait")}");
    Console.WriteLine($"\tPaper size:\t\t{pageInfo.PaperSize} ({pageInfo.WidthInPoints:F0}x{pageInfo.HeightInPoints:F0}pt)");
    Console.WriteLine($"\tSize in points:\t{pageInfo.SizeInPoints}");
    Console.WriteLine($"\tSize in pixels:\t{pageInfo.GetSizeInPixels(1.0f, 96)} at {scale * 100}% scale, {dpi} dpi");

    // Kaynak tepsi bilgilerini yazdırın.
    Console.WriteLine($"\tTray:\t{pageInfo.PaperTray}");
    PaperSource source = pageInfo.GetSpecifiedPrinterPaperSource(paperSources, paperSources[0]);
    Console.WriteLine($"\tSuitable print source:\t{source.SourceName}, kind: {source.Kind}");
}
```

### Ayrıca bakınız

* ad alanı [Aspose.Words.Rendering](../../aspose.words.rendering/)
* toplantı [Aspose.Words](../../)


