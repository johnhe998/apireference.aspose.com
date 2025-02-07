---
title: ShapeBase.GetShapeRenderer
second_title: Aspose.Words for .NET API Referansı
description: ShapeBase yöntem. Bu şekli bir görüntüye dönüştürmek için kullanılabilecek bir nesne oluşturur ve döndürür.
type: docs
weight: 600
url: /tr/net/aspose.words.drawing/shapebase/getshaperenderer/
---
## ShapeBase.GetShapeRenderer method

Bu şekli bir görüntüye dönüştürmek için kullanılabilecek bir nesne oluşturur ve döndürür.

```csharp
public ShapeRenderer GetShapeRenderer()
```

### Geri dönüş değeri

Bu şeklin oluşturucu nesnesi.

### Notlar

Bu yöntem sadece[`ShapeRenderer`](../../../aspose.words.rendering/shaperenderer/) yapıcı ve bu nesneyi parametre olarak pass iletir.

### Örnekler

Şekilleri yerel dosya sistemindeki dosyalara dışa aktarmak için bir şekil oluşturucunun nasıl kullanılacağını gösterir.

```csharp
Document doc = new Document(MyDir + "Various shapes.docx");
Shape[] shapes = doc.GetChildNodes(NodeType.Shape, true).OfType<Shape>().ToArray();

Assert.AreEqual(7, shapes.Length);

// Belgede 2 alt şekil içeren bir grup şekli de dahil olmak üzere 7 şekil var.
// Her şekli yerel dosya sisteminde bir görüntü dosyasına dönüştüreceğiz
// grup şekillerini, görünümleri olmadığı için yok sayarken.
// Bu, 6 görüntü dosyası üretecektir.
foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true).OfType<Shape>())
{
    ShapeRenderer renderer = shape.GetShapeRenderer();
    ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Png);
    renderer.Save(ArtifactsDir + $"Shape.RenderAllShapes.{shape.Name}.png", options);
}
```

### Ayrıca bakınız

* class [ShapeRenderer](../../../aspose.words.rendering/shaperenderer/)
* class [ShapeBase](../)
* ad alanı [Aspose.Words.Drawing](../../shapebase/)
* toplantı [Aspose.Words](../../../)


