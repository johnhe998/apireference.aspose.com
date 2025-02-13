---
title: Enum ColorMode
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Saving.ColorMode Sıralama. Renklerin nasıl oluşturulacağını belirtir.
type: docs
weight: 4600
url: /tr/net/aspose.words.saving/colormode/
---
## ColorMode enumeration

Renklerin nasıl oluşturulacağını belirtir.

```csharp
public enum ColorMode
```

### değerler

| İsim | Değer | Tanım |
| --- | --- | --- |
| Normal | `0` | Değiştirilmemiş renklerle işleme. |
| Grayscale | `1` | Beyazdan siyaha çeşitli gri tonlarında renklerle işleme. |

### Örnekler

Seçenekleri kaydetme özelliği ile görüntü renginin nasıl değiştirileceğini gösterir.

```csharp
Document doc = new Document(MyDir + "Images.docx");

// Belgenin "Kaydet" yöntemine aktarabileceğimiz bir "PdfSaveOptions" nesnesi oluşturun
// bu yöntemin belgeyi .PDF'ye dönüştürme şeklini değiştirmek için.
// Belgedeki tüm görüntüleri siyah beyaz işlemek için "ColorMode" özelliğini "Gri Tonlamalı" olarak ayarlayın.
// Çıktı belgesinin boyutu bu ayarla daha büyük olabilir.
// Tüm görüntüleri renkli hale getirmek için "ColorMode" özelliğini "Normal" olarak ayarlayın.
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions { ColorMode = colorMode };

doc.Save(ArtifactsDir + "PdfSaveOptions.ColorRendering.pdf", pdfSaveOptions);
```

### Ayrıca bakınız

* ad alanı [Aspose.Words.Saving](../../aspose.words.saving/)
* toplantı [Aspose.Words](../../)


