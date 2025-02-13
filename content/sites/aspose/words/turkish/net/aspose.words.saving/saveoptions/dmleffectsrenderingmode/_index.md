---
title: SaveOptions.DmlEffectsRenderingMode
second_title: Aspose.Words for .NET API Referansı
description: SaveOptions mülk. DrawingML efektlerinin nasıl oluşturulacağını belirleyen bir değer alır veya ayarlar.
type: docs
weight: 60
url: /tr/net/aspose.words.saving/saveoptions/dmleffectsrenderingmode/
---
## SaveOptions.DmlEffectsRenderingMode property

DrawingML efektlerinin nasıl oluşturulacağını belirleyen bir değer alır veya ayarlar.

```csharp
public virtual DmlEffectsRenderingMode DmlEffectsRenderingMode { get; set; }
```

### Notlar

Varsayılan değerSimplified .

Bu özellik, belge sabit sayfa biçimlerine dışa aktarıldığında kullanılır.

### Örnekler

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

* enum [DmlEffectsRenderingMode](../../dmleffectsrenderingmode/)
* class [SaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../saveoptions/)
* toplantı [Aspose.Words](../../../)


