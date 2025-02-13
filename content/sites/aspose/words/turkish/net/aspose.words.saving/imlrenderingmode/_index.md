---
title: Enum ImlRenderingMode
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Saving.ImlRenderingMode Sıralama. Mürekkep InkML nesnelerinin nasıl sabit sayfa biçimlerine dönüştürüleceğini belirtir.
type: docs
weight: 4990
url: /tr/net/aspose.words.saving/imlrenderingmode/
---
## ImlRenderingMode enumeration

Mürekkep (InkML) nesnelerinin nasıl sabit sayfa biçimlerine dönüştürüleceğini belirtir.

```csharp
public enum ImlRenderingMode
```

### değerler

| İsim | Değer | Tanım |
| --- | --- | --- |
| Fallback | `0` | Ink (InkML) nesnesi için geri dönüş şekli mevcutsa, Aspose.Words, InkML. yerine geri dönüş şekli oluşturur. |
| InkML | `1` | Aspose.Words, mürekkep (InkML) nesnesinin geri dönüş şeklini yok sayar ve InkML'nin kendisini oluşturur. Bu, varsayılan moddur. |

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

* ad alanı [Aspose.Words.Saving](../../aspose.words.saving/)
* toplantı [Aspose.Words](../../)


