---
title: Enum WatermarkLayout
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.WatermarkLayout Sıralama. Filigran merkezine göre filigranın düzenini tanımlar.
type: docs
weight: 6370
url: /tr/net/aspose.words/watermarklayout/
---
## WatermarkLayout enumeration

Filigran merkezine göre filigranın düzenini tanımlar.

```csharp
public enum WatermarkLayout
```

### değerler

| İsim | Değer | Tanım |
| --- | --- | --- |
| Horizontal | `0` | Yatay filigran düzeni. 0 derecelik dönüşe karşılık gelir. |
| Diagonal | `315` | Çapraz filigran düzeni. 315 derecelik dönüşe karşılık gelir. |

### Örnekler

Metin filigranının nasıl oluşturulacağını gösterir.

```csharp
Document doc = new Document();

// Düz metin filigranı ekleyin.
doc.Watermark.SetText("Aspose Watermark");

// Metin biçimlendirmesini filigran olarak kullanarak düzenlemek istiyorsak,
// filigran oluştururken bir TextWatermarkOptions nesnesi ileterek bunu yapabiliriz.
TextWatermarkOptions textWatermarkOptions = new TextWatermarkOptions();
textWatermarkOptions.FontFamily = "Arial";
textWatermarkOptions.FontSize = 36;
textWatermarkOptions.Color = Color.Black;
textWatermarkOptions.Layout = WatermarkLayout.Diagonal;
textWatermarkOptions.IsSemitrasparent = false;

doc.Watermark.SetText("Aspose Watermark", textWatermarkOptions);

doc.Save(ArtifactsDir + "Document.TextWatermark.docx");

// Böyle bir belgeden bir filigranı kaldırabiliriz.
if (doc.Watermark.Type == WatermarkType.Text)
    doc.Watermark.Remove();
```

### Ayrıca bakınız

* ad alanı [Aspose.Words](../../aspose.words/)
* toplantı [Aspose.Words](../../)


