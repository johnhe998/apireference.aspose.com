---
title: SaveOptions.ImlRenderingMode
second_title: Aspose.Words for .NET API Referansı
description: SaveOptions mülk. Mürekkep InkML nesnelerinin nasıl oluşturulacağını belirleyen bir değer alır veya ayarlar.
type: docs
weight: 100
url: /tr/net/aspose.words.saving/saveoptions/imlrenderingmode/
---
## SaveOptions.ImlRenderingMode property

Mürekkep (InkML) nesnelerinin nasıl oluşturulacağını belirleyen bir değer alır veya ayarlar.

```csharp
public ImlRenderingMode ImlRenderingMode { get; set; }
```

### Notlar

Varsayılan değerInkML .

Bu özellik, belge sabit sayfa biçimlerine dışa aktarıldığında kullanılır.

### Örnekler

Ink nesnesinin nasıl oluşturulacağını gösterir.

```csharp
Document doc = new Document(MyDir + "Ink object.docx");

// 'ImlRenderingMode.InkML' ayarı, mürekkep (InkML) nesnesinin geri dönüş şeklini yok sayar ve InkML'nin kendisini oluşturur.
// Oluşturma sonucu tatmin edici değilse,
// önceki sürümlere benzer bir sonuç elde etmek için lütfen 'ImlRenderingMode.Fallback' kullanın.
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Jpeg)
{
    ImlRenderingMode = ImlRenderingMode.InkML
};

doc.Save(ArtifactsDir + "ImageSaveOptions.RenderInkObject.jpeg", saveOptions);
```

### Ayrıca bakınız

* enum [ImlRenderingMode](../../imlrenderingmode/)
* class [SaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../saveoptions/)
* toplantı [Aspose.Words](../../../)


