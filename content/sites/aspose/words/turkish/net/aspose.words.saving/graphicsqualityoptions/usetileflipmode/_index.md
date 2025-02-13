---
title: GraphicsQualityOptions.UseTileFlipMode
second_title: Aspose.Words for .NET API Referansı
description: GraphicsQualityOptions mülk. WrapModeun TileFlipXY olup olmadığını belirten bir bayrak alır veya ayarlar.
type: docs
weight: 80
url: /tr/net/aspose.words.saving/graphicsqualityoptions/usetileflipmode/
---
## GraphicsQualityOptions.UseTileFlipMode property

WrapMode'un TileFlipXY olup olmadığını belirten bir bayrak alır veya ayarlar.

```csharp
public bool UseTileFlipMode { get; set; }
```

### Notlar

buWrapMode doldurulan alandan daha küçük olduğunda bir doku veya degradenin nasıl döşeneceğini belirtir.

Varsayılan olarak kullanırTile (çevirmeden döşemeyi belirtir). Bu, ölçeklenen görüntünün (yüksek çözünürlüklü) hatalı oluşturulmasına neden olur.

Bu özellik WrapMode'u şu şekilde değiştirmeye izin verir:TileFlipXY (bir satır boyunca hareket ederken döşemelerin yatay olarak çevrildiğini ve bir sütun boyunca hareket ederken dikey olarak çevrildiğini belirtir).

### Örnekler

Yüksek çözünürlükte render alırken beyaz çizginin nasıl önleneceğini gösterir.

```csharp
Document doc = new Document(MyDir + "Shape high dpi.docx");

Shape shape = (Shape)doc.GetChild(NodeType.Shape, 0, true);
ShapeRenderer renderer = shape.GetShapeRenderer();

ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
{
    Resolution = 500, GraphicsQualityOptions = new GraphicsQualityOptions { UseTileFlipMode = true }
};
renderer.Save(ArtifactsDir + "ImageSaveOptions.UseTileFlipMode.png", saveOptions);
```

### Ayrıca bakınız

* class [GraphicsQualityOptions](../)
* ad alanı [Aspose.Words.Saving](../../graphicsqualityoptions/)
* toplantı [Aspose.Words](../../../)


