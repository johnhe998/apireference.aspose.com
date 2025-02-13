---
title: NodeRendererBase.Save
second_title: Aspose.Words for .NET API Referansı
description: NodeRendererBase yöntem. Şekli bir görüntüye dönüştürür ve bir dosyaya kaydeder.
type: docs
weight: 90
url: /tr/net/aspose.words.rendering/noderendererbase/save/
---
## Save(string, ImageSaveOptions) {#save_1}

Şekli bir görüntüye dönüştürür ve bir dosyaya kaydeder.

```csharp
public void Save(string fileName, ImageSaveOptions saveOptions)
```

| Parametre | Tip | Tanım |
| --- | --- | --- |
| fileName | String | Görüntü dosyasının adı. Belirtilen ada sahip bir dosya zaten varsa, mevcut dosyanın üzerine yazılır. |
| saveOptions | ImageSaveOptions | Şeklin nasıl oluşturulacağını ve kaydedileceğini denetleyen seçenekleri belirtir. Boş olabilir. |

### Örnekler

Yerel dosya sisteminde bir Office Math nesnesinin bir görüntü dosyasına nasıl dönüştürüleceğini gösterir.

```csharp
Document doc = new Document(MyDir + "Office math.docx");

OfficeMath math = (OfficeMath)doc.GetChild(NodeType.OfficeMath, 0, true);

// Düğüm oluşturucunun değiştirilecek "Kaydet" yöntemine geçmek için bir "ImageSaveOptions" nesnesi oluşturun
// OfficeMath düğümünü bir görüntüye nasıl dönüştürdüğü.
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png);

// Nesneyi orijinal boyutunun beş katına çıkarmak için "Scale" özelliğini 5'e ayarlayın.
saveOptions.Scale = 5;

math.GetMathRenderer().Save(ArtifactsDir + "Shape.RenderOfficeMath.png", saveOptions);
```

### Ayrıca bakınız

* class [ImageSaveOptions](../../../aspose.words.saving/imagesaveoptions/)
* class [NodeRendererBase](../)
* ad alanı [Aspose.Words.Rendering](../../noderendererbase/)
* toplantı [Aspose.Words](../../../)

---

## Save(Stream, ImageSaveOptions) {#save}

Şekli bir görüntüye dönüştürür ve bir akışa kaydeder.

```csharp
public void Save(Stream stream, ImageSaveOptions saveOptions)
```

| Parametre | Tip | Tanım |
| --- | --- | --- |
| stream | Stream | Şeklin görüntüsünün kaydedileceği akış. |
| saveOptions | ImageSaveOptions | Şeklin nasıl oluşturulacağını ve kaydedileceğini denetleyen seçenekleri belirtir. null olabilir. Bu null ise, resim PNG formatında kaydedilir. |

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

* class [ImageSaveOptions](../../../aspose.words.saving/imagesaveoptions/)
* class [NodeRendererBase](../)
* ad alanı [Aspose.Words.Rendering](../../noderendererbase/)
* toplantı [Aspose.Words](../../../)


