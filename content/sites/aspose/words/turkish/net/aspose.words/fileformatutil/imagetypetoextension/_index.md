---
title: FileFormatUtil.ImageTypeToExtension
second_title: Aspose.Words for .NET API Referansı
description: FileFormatUtil yöntem. Aspose.Words görüntü tipi numaralandırılmış bir değeri bir dosya uzantısına dönüştürür. Döndürülen uzantı başında nokta bulunan küçük harfli bir dizedir.
type: docs
weight: 50
url: /tr/net/aspose.words/fileformatutil/imagetypetoextension/
---
## FileFormatUtil.ImageTypeToExtension method

Aspose.Words görüntü tipi numaralandırılmış bir değeri bir dosya uzantısına dönüştürür. Döndürülen uzantı, başında nokta bulunan küçük harfli bir dizedir.

```csharp
public static string ImageTypeToExtension(ImageType imageType)
```

### istisnalar

| istisna | şart |
| --- | --- |
| ArgumentException | Dönüştürülemediğinde atar. |

### Örnekler

Bir belgeden görüntülerin nasıl çıkarılacağını ve bunların yerel dosya sistemine ayrı dosyalar olarak nasıl kaydedileceğini gösterir.

```csharp
Document doc = new Document(MyDir + "Images.docx");

// Belgeden şekil koleksiyonunu alın,
// ve bir görüntü ile her şeklin görüntü verilerini yerel dosya sistemine dosya olarak kaydedin.
NodeCollection shapes = doc.GetChildNodes(NodeType.Shape, true);

Assert.AreEqual(9, shapes.Count(s => ((Shape)s).HasImage));

int imageIndex = 0;
foreach (Shape shape in shapes.OfType<Shape>())
{
    if (shape.HasImage)
    {
        // Şekillerin görüntü verileri, birçok olası görüntü formatının görüntülerini içerebilir. 
        // Her resim için formatına göre otomatik olarak bir dosya uzantısı belirleyebiliriz.
        string imageFileName =
            $"File.ExtractImages.{imageIndex}{FileFormatUtil.ImageTypeToExtension(shape.ImageData.ImageType)}";
        shape.ImageData.Save(ArtifactsDir + imageFileName);
        imageIndex++;
    }
}
```

### Ayrıca bakınız

* enum [ImageType](../../../aspose.words.drawing/imagetype/)
* class [FileFormatUtil](../)
* ad alanı [Aspose.Words](../../fileformatutil/)
* toplantı [Aspose.Words](../../../)


