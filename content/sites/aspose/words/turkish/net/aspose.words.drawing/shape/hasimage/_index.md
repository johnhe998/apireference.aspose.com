---
title: Shape.HasImage
second_title: Aspose.Words for .NET API Referansı
description: Shape mülk. Şekilde görüntü baytları varsa veya bir görüntüye bağlanırsa true değerini döndürür.
type: docs
weight: 80
url: /tr/net/aspose.words.drawing/shape/hasimage/
---
## Shape.HasImage property

Şekilde görüntü baytları varsa veya bir görüntüye bağlanırsa true değerini döndürür.

```csharp
public bool HasImage { get; }
```

### Örnekler

Bir belgeden görüntülü tüm şekillerin nasıl silineceğini gösterir.

```csharp
Document doc = new Document(MyDir + "Images.docx");
NodeCollection shapes = doc.GetChildNodes(NodeType.Shape, true);

Assert.AreEqual(9, shapes.OfType<Shape>().Count(s => s.HasImage));

foreach (Shape shape in shapes.OfType<Shape>())
    if (shape.HasImage) 
        shape.Remove();

Assert.AreEqual(0, shapes.OfType<Shape>().Count(s => s.HasImage));
```

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

* class [Shape](../)
* ad alanı [Aspose.Words.Drawing](../../shape/)
* toplantı [Aspose.Words](../../../)


