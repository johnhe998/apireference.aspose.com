---
title: Class FrameFormat
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.FrameFormat sınıf. Bir paragraf için çerçeveyle ilgili biçimlendirmeyi temsil eder.
type: docs
weight: 2890
url: /tr/net/aspose.words/frameformat/
---
## FrameFormat class

Bir paragraf için çerçeveyle ilgili biçimlendirmeyi temsil eder.

```csharp
public class FrameFormat
```

## Özellikleri

| İsim | Tanım |
| --- | --- |
| [Height](../../aspose.words/frameformat/height/) { get; } | Belirtilen çerçevenin yüksekliğini alır. |
| [HeightRule](../../aspose.words/frameformat/heightrule/) { get; } | Belirtilen çerçevenin yüksekliğini belirleme kuralını alır. |
| [HorizontalAlignment](../../aspose.words/frameformat/horizontalalignment/) { get; } | Belirtilen çerçevenin yatay hizalamasını alır. |
| [HorizontalDistanceFromText](../../aspose.words/frameformat/horizontaldistancefromtext/) { get; } | Bir çerçeve ile çevresindeki metin arasındaki yatay mesafeyi nokta olarak alır. |
| [HorizontalPosition](../../aspose.words/frameformat/horizontalposition/) { get; } | Çerçevenin kenarı ile belirtilen öğe arasındaki yatay mesafeyi alır.[`RelativeHorizontalPosition`](./relativehorizontalposition/) özellik. |
| [IsFrame](../../aspose.words/frameformat/isframe/) { get; } | Paragraf bir çerçeve ise true değerini döndürür. |
| [RelativeHorizontalPosition](../../aspose.words/frameformat/relativehorizontalposition/) { get; } | Bir çerçevenin göreli yatay konumunu alır. |
| [RelativeVerticalPosition](../../aspose.words/frameformat/relativeverticalposition/) { get; } | Bir çerçevenin göreli dikey konumunu alır. |
| [VerticalAlignment](../../aspose.words/frameformat/verticalalignment/) { get; } | Belirtilen çerçevenin dikey hizalamasını alır. |
| [VerticalDistanceFromText](../../aspose.words/frameformat/verticaldistancefromtext/) { get; } | Bir çerçeve ile çevresindeki metin arasındaki dikey mesafeyi (nokta olarak) belirtir. |
| [VerticalPosition](../../aspose.words/frameformat/verticalposition/) { get; } | Çerçevenin kenarı ile belirtilen öğe arasındaki dikey mesafeyi alır.[`RelativeVerticalPosition`](./relativeverticalposition/) özellik. |
| [Width](../../aspose.words/frameformat/width/) { get; } | Belirtilen çerçevenin genişliğini puan cinsinden alır. |

### Notlar

Bu nesne her zaman oluşturulur. Bir paragraf bir çerçeveyse, tüm özellikler ilgili değerleri içerecektir, aksi takdirde tüm özellikler varsayılanlarına ayarlanır.

Kullanmak[`IsFrame`](./isframe/) paragrafın bir çerçeve olup olmadığını kontrol etmek için.

### Örnekler

Çerçeve olan paragrafların biçimlendirme özellikleri hakkında nasıl bilgi alınacağını gösterir.

```csharp
Document doc = new Document(MyDir + "Paragraph frame.docx");

Paragraph paragraphFrame = doc.FirstSection.Body.Paragraphs.OfType<Paragraph>().First(p => p.FrameFormat.IsFrame);

Assert.AreEqual(233.3d, paragraphFrame.FrameFormat.Width);
Assert.AreEqual(138.8d, paragraphFrame.FrameFormat.Height);
Assert.AreEqual(HeightRule.AtLeast, paragraphFrame.FrameFormat.HeightRule);
Assert.AreEqual(HorizontalAlignment.Default, paragraphFrame.FrameFormat.HorizontalAlignment);
Assert.AreEqual(VerticalAlignment.Default, paragraphFrame.FrameFormat.VerticalAlignment);
Assert.AreEqual(34.05d, paragraphFrame.FrameFormat.HorizontalPosition);
Assert.AreEqual(RelativeHorizontalPosition.Page, paragraphFrame.FrameFormat.RelativeHorizontalPosition);
Assert.AreEqual(9.0d, paragraphFrame.FrameFormat.HorizontalDistanceFromText);
Assert.AreEqual(20.5d, paragraphFrame.FrameFormat.VerticalPosition);
Assert.AreEqual(RelativeVerticalPosition.Paragraph, paragraphFrame.FrameFormat.RelativeVerticalPosition);
Assert.AreEqual(0.0d, paragraphFrame.FrameFormat.VerticalDistanceFromText);
```

### Ayrıca bakınız

* ad alanı [Aspose.Words](../../aspose.words/)
* toplantı [Aspose.Words](../../)


