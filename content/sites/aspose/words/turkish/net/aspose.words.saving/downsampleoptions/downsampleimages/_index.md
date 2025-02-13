---
title: DownsampleOptions.DownsampleImages
second_title: Aspose.Words for .NET API Referansı
description: DownsampleOptions mülk. Görüntülerin altörneklenmesi gerekip gerekmediğini belirtir.
type: docs
weight: 20
url: /tr/net/aspose.words.saving/downsampleoptions/downsampleimages/
---
## DownsampleOptions.DownsampleImages property

Görüntülerin altörneklenmesi gerekip gerekmediğini belirtir.

```csharp
public bool DownsampleImages { get; set; }
```

### Notlar

Varsayılan değer`doğru` .

### Örnekler

PDF belgesindeki görüntülerin çözünürlüğünün nasıl değiştirileceğini gösterir.

```csharp
Document doc = new Document(MyDir + "Images.docx");

// Belgenin "Kaydet" yöntemine aktarabileceğimiz bir "PdfSaveOptions" nesnesi oluşturun
// bu yöntemin belgeyi .PDF'ye dönüştürme şeklini değiştirmek için.
PdfSaveOptions options = new PdfSaveOptions();

// Varsayılan olarak Aspose.Words, PDF'ye kaydettiğimiz bir belgedeki tüm görüntüleri 220 ppi'ye düşürür.
Assert.True(options.DownsampleOptions.DownsampleImages);
Assert.AreEqual(220, options.DownsampleOptions.Resolution);
Assert.AreEqual(0, options.DownsampleOptions.ResolutionThreshold);

doc.Save(ArtifactsDir + "PdfSaveOptions.DownsampleOptions.Default.pdf", options);

// Tüm görüntüleri 36 ppi'ye düşürmek için "Çözünürlük" özelliğini "36" olarak ayarlayın.
options.DownsampleOptions.Resolution = 36;

// "ResolutionThreshold" özelliğini yalnızca altörneklemeyi
// çözünürlüğü 128 ppi'nin üzerinde olan görüntüler.
options.DownsampleOptions.ResolutionThreshold = 128;

// Bu aşamada belgeden yalnızca ilk iki görüntü altörneklenecektir.
doc.Save(ArtifactsDir + "PdfSaveOptions.DownsampleOptions.LowerResolution.pdf", options);
```

### Ayrıca bakınız

* class [DownsampleOptions](../)
* ad alanı [Aspose.Words.Saving](../../downsampleoptions/)
* toplantı [Aspose.Words](../../../)


