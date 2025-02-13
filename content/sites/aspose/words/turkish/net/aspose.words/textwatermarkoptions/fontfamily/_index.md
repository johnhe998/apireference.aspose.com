---
title: TextWatermarkOptions.FontFamily
second_title: Aspose.Words for .NET API Referansı
description: TextWatermarkOptions mülk. Yazı tipi aile adını alır veya ayarlar. Varsayılan değer Calibridir.
type: docs
weight: 30
url: /tr/net/aspose.words/textwatermarkoptions/fontfamily/
---
## TextWatermarkOptions.FontFamily property

Yazı tipi aile adını alır veya ayarlar. Varsayılan değer "Calibri"dir.

```csharp
public string FontFamily { get; set; }
```

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

* class [TextWatermarkOptions](../)
* ad alanı [Aspose.Words](../../textwatermarkoptions/)
* toplantı [Aspose.Words](../../../)


