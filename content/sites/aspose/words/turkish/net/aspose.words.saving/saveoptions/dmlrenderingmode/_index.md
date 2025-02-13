---
title: SaveOptions.DmlRenderingMode
second_title: Aspose.Words for .NET API Referansı
description: SaveOptions mülk. DrawingML şekillerinin nasıl oluşturulacağını belirleyen bir değer alır veya ayarlar.
type: docs
weight: 70
url: /tr/net/aspose.words.saving/saveoptions/dmlrenderingmode/
---
## SaveOptions.DmlRenderingMode property

DrawingML şekillerinin nasıl oluşturulacağını belirleyen bir değer alır veya ayarlar.

```csharp
public DmlRenderingMode DmlRenderingMode { get; set; }
```

### Notlar

Varsayılan değerFallback .

Bu özellik, belge sabit sayfa biçimlerine dışa aktarıldığında kullanılır.

### Örnekler

PDF'ye kaydederken yedek şekillerin nasıl oluşturulacağını gösterir.

```csharp
Document doc = new Document(MyDir + "DrawingML shape fallbacks.docx");

// Belgenin "Kaydet" yöntemine aktarabileceğimiz bir "PdfSaveOptions" nesnesi oluşturun
// bu yöntemin belgeyi .PDF'ye dönüştürme şeklini değiştirmek için.
PdfSaveOptions options = new PdfSaveOptions();

// "DmlRenderingMode" özelliğini "DmlRenderingMode.Fallback" olarak ayarlayın
// DML şekillerini yedek şekilleriyle değiştirmek için.
// "DmlRenderingMode" özelliğini "DmlRenderingMode.DrawingML" olarak ayarlayın
// DML şekillerini kendileri oluşturmak için.
options.DmlRenderingMode = dmlRenderingMode;

doc.Save(ArtifactsDir + "PdfSaveOptions.DrawingMLFallback.pdf", options);
```

Bir belgeyi PDF'ye kaydederken, DrawingML efektlerinin oluşturma kalitesinin nasıl yapılandırılacağını gösterir.

```csharp
Document doc = new Document(MyDir + "DrawingML shape effects.docx");

// Belgenin "Kaydet" yöntemine aktarabileceğimiz bir "PdfSaveOptions" nesnesi oluşturun
// bu yöntemin belgeyi .PDF'ye dönüştürme şeklini değiştirmek için.
PdfSaveOptions options = new PdfSaveOptions();

// Tüm DrawingML efektlerini atmak için "DmlEffectsRenderingMode" özelliğini "DmlEffectsRenderingMode.None" olarak ayarlayın.
// "DmlEffectsRenderingMode" özelliğini "DmlEffectsRenderingMode.Simplified" olarak ayarlayın
// DrawingML efektlerinin basitleştirilmiş bir sürümünü oluşturmak için.
// "DmlEffectsRenderingMode" özelliğini "DmlEffectsRenderingMode.Fine" olarak ayarlayın.
// DrawingML efektlerini daha doğru bir şekilde ve ayrıca daha fazla işlem maliyetiyle işleyin.
options.DmlEffectsRenderingMode = effectsRenderingMode;

Assert.AreEqual(DmlRenderingMode.DrawingML, options.DmlRenderingMode);

doc.Save(ArtifactsDir + "PdfSaveOptions.DrawingMLEffects.pdf", options);
```

### Ayrıca bakınız

* enum [DmlRenderingMode](../../dmlrenderingmode/)
* class [SaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../saveoptions/)
* toplantı [Aspose.Words](../../../)


