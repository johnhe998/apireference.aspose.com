---
title: ShapeBase.ZOrder
second_title: Aspose.Words for .NET API Referansı
description: ShapeBase mülk. Çakışan şekillerin görüntülenme sırasını belirler.
type: docs
weight: 550
url: /tr/net/aspose.words.drawing/shapebase/zorder/
---
## ShapeBase.ZOrder property

Çakışan şekillerin görüntülenme sırasını belirler.

```csharp
public int ZOrder { get; set; }
```

### Notlar

Yalnızca üst düzey şekiller için etkilidir.

Varsayılan değer 0'dır.

Sayı, yığınlama önceliğini temsil eder. Daha yüksek numaralı bir şekil, daha düşük numaralı bir şeklin ("önünde") örtüşüyormuş gibi görüntülenecektir .

Üst üste binen şekillerin sırası, başlıktaki ve belgenin main metnindeki şekiller için bağımsızdır.

Bir grup şeklindeki alt şekillerin görüntülenme sırası, grup şekli içindeki order tarafından belirlenir.

### Örnekler

Şekillerin sırasının nasıl değiştirileceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Birbiriyle kısmen örtüşen üç farklı renkli dikdörtgen ekleyin.
// Başka bir şekille örtüşen bir şekil eklediğimizde Aspose.Words yeni şekli eski şeklin üzerine yerleştirir.
// Açık yeşil dikdörtgen, açık mavi dikdörtgenin üzerine gelecek ve onu kısmen gizleyecektir,
// ve açık mavi dikdörtgen turuncu dikdörtgeni gizleyecektir.
Shape shape = builder.InsertShape(ShapeType.Rectangle, RelativeHorizontalPosition.LeftMargin, 100,
    RelativeVerticalPosition.TopMargin, 100, 200, 200, WrapType.None);
shape.FillColor = Color.Orange;

shape = builder.InsertShape(ShapeType.Rectangle, RelativeHorizontalPosition.LeftMargin, 150,
    RelativeVerticalPosition.TopMargin, 150, 200, 200, WrapType.None);
shape.FillColor = Color.LightBlue;

shape = builder.InsertShape(ShapeType.Rectangle, RelativeHorizontalPosition.LeftMargin, 200,
    RelativeVerticalPosition.TopMargin, 200, 200, 200, WrapType.None);
shape.FillColor = Color.LightGreen;

Shape[] shapes = doc.GetChildNodes(NodeType.Shape, true).OfType<Shape>().ToArray();

// Bir şeklin "ZOrder" özelliği, üst üste binen diğer şekiller arasında yığma önceliğini belirler.
// Örtüşen iki şekil farklı "ZOrder" değerlerine sahipse,
 // Microsoft Word, değeri yüksek olan şekli, değeri düşük olan şeklin üzerine yerleştirir.
// İlk turuncu dikdörtgeni ikinci açık mavi dikdörtgenin üzerine yerleştirmek için şekillerimizin "ZOrder" değerlerini ayarlayın
// ve üçüncü açık yeşil dikdörtgenin üzerindeki ikinci açık mavi dikdörtgen.
// Bu, orijinal istifleme sırasını tersine çevirir.
shapes[0].ZOrder = 3;
shapes[1].ZOrder = 2;
shapes[2].ZOrder = 1;

doc.Save(ArtifactsDir + "Shape.ZOrder.docx");
```

### Ayrıca bakınız

* class [ShapeBase](../)
* ad alanı [Aspose.Words.Drawing](../../shapebase/)
* toplantı [Aspose.Words](../../../)


