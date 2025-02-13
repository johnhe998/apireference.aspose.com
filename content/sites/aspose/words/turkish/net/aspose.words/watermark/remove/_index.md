---
title: Watermark.Remove
second_title: Aspose.Words for .NET API Referansı
description: Watermark yöntem. Filigranı kaldırır.
type: docs
weight: 20
url: /tr/net/aspose.words/watermark/remove/
---
## Watermark.Remove method

Filigranı kaldırır.

```csharp
public void Remove()
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

* class [Watermark](../)
* ad alanı [Aspose.Words](../../watermark/)
* toplantı [Aspose.Words](../../../)


