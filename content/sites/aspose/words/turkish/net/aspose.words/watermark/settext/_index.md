---
title: Watermark.SetText
second_title: Aspose.Words for .NET API Referansı
description: Watermark yöntem. Belgeye Metin filigranı ekler.
type: docs
weight: 40
url: /tr/net/aspose.words/watermark/settext/
---
## SetText(string) {#settext}

Belgeye Metin filigranı ekler.

```csharp
public void SetText(string text)
```

| Parametre | Tip | Tanım |
| --- | --- | --- |
| text | String | Filigran olarak görüntülenen metin. |

### istisnalar

| istisna | şart |
| --- | --- |
| ArgumentOutOfRangeException | Metin uzunluğu aralık dışında olduğunda veya metin yalnızca boşluklar içerdiğinde atar. |
| ArgumentNullException | Metin boş olduğunda atar. |

### Notlar

Metin uzunluğu 1 ile 200 arasında olmalıdır. Metin boş olamaz veya yalnızca boşluklar içerebilir.

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

---

## SetText(string, TextWatermarkOptions) {#settext_1}

Belgeye Metin filigranı ekler.

```csharp
public void SetText(string text, TextWatermarkOptions options)
```

| Parametre | Tip | Tanım |
| --- | --- | --- |
| text | String | Filigran olarak görüntülenen metin. |
| options | TextWatermarkOptions | Metin filigranı için ek seçenekleri tanımlar. |

### istisnalar

| istisna | şart |
| --- | --- |
| ArgumentOutOfRangeException | Metin uzunluğu aralık dışında olduğunda veya metin yalnızca boşluklar içerdiğinde atar. |
| ArgumentNullException | Metin boş olduğunda atar. |

### Notlar

Metin uzunluğu 1 ile 200 arasında olmalıdır. Metin boş olamaz veya yalnızca boşluklar içerebilir.

Eğer[`TextWatermarkOptions`](../../textwatermarkoptions/) null ise filigran varsayılan seçeneklerle ayarlanacaktır.

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

* class [TextWatermarkOptions](../../textwatermarkoptions/)
* class [Watermark](../)
* ad alanı [Aspose.Words](../../watermark/)
* toplantı [Aspose.Words](../../../)


