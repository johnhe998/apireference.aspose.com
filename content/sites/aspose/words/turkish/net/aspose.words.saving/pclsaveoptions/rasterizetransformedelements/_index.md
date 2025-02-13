---
title: PclSaveOptions.RasterizeTransformedElements
second_title: Aspose.Words for .NET API Referansı
description: PclSaveOptions mülk. Karmaşık dönüştürülmüş öğelerin PCL belgesine kaydedilmeden önce rasterleştirilmesi gerekip gerekmediğini belirleyen bir değer alır veya ayarlar. Varsayılandoğru .
type: docs
weight: 30
url: /tr/net/aspose.words.saving/pclsaveoptions/rasterizetransformedelements/
---
## PclSaveOptions.RasterizeTransformedElements property

Karmaşık dönüştürülmüş öğelerin PCL belgesine kaydedilmeden önce rasterleştirilmesi gerekip gerekmediğini belirleyen bir değer alır veya ayarlar. Varsayılan`doğru` .

```csharp
public bool RasterizeTransformedElements { get; set; }
```

### Notlar

PCL, Aspose Words tarafından kullanılan bazı dönüştürme türlerini desteklemez. Örneğin döndürülmüş, eğik görüntüler ve doku fırçaları. Bu tür öğeleri düzgün bir şekilde oluşturmak için rasterleştirme işlemi kullanılır, yani görüntüye kaydetme ve kırpma. Bu işlem ek zaman ve bellek alabilir. Bayrak olarak ayarlanırsa`yanlış` çıktıdaki bazı içerikler kaynak belgeyle karşılaştırıldığında farklı olabilir.

### Örnekler

Bir belgeyi PCL'ye kaydederken karmaşık öğelerin nasıl rasterleştirileceğini gösterir.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

PclSaveOptions saveOptions = new PclSaveOptions
{
    SaveFormat = SaveFormat.Pcl,
    RasterizeTransformedElements = true
};

doc.Save(ArtifactsDir + "PclSaveOptions.RasterizeElements.pcl", saveOptions);
```

### Ayrıca bakınız

* class [PclSaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../pclsaveoptions/)
* toplantı [Aspose.Words](../../../)


