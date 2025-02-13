---
title: ShapeBase.BoundsWithEffects
second_title: Aspose.Words for .NET API Referansı
description: ShapeBase mülk. Çizim efektleri uygulandıktan sonra bu şekil nesnesinin sahip olduğu son kapsamı alır. Değer noktalarla ölçülür.
type: docs
weight: 90
url: /tr/net/aspose.words.drawing/shapebase/boundswitheffects/
---
## ShapeBase.BoundsWithEffects property

Çizim efektleri uygulandıktan sonra bu şekil nesnesinin sahip olduğu son kapsamı alır. Değer, noktalarla ölçülür.

```csharp
public RectangleF BoundsWithEffects { get; }
```

### Örnekler

Bir şeklin sınırlarının şekil efektlerinden nasıl etkilendiğinin nasıl kontrol edileceğini gösterir.

```csharp
Document doc = new Document(MyDir + "Shape shadow effect.docx");

Shape[] shapes = doc.GetChildNodes(NodeType.Shape, true).OfType<Shape>().ToArray();

Assert.AreEqual(2, shapes.Length);

// İki şekil, boyut ve şekil türü açısından aynıdır.
Assert.AreEqual(shapes[0].Width, shapes[1].Width);
Assert.AreEqual(shapes[0].Height, shapes[1].Height);
Assert.AreEqual(shapes[0].ShapeType, shapes[1].ShapeType);

// İlk şeklin etkisi yoktur ve ikinci şeklin gölgeli ve kalın dış hatları vardır.
// Bu efektler, ikinci şeklin siluetinin boyutunu birinciden daha büyük yapar.
// Microsoft Word'de bu şekillere tıkladığımızda dikdörtgenin boyutu görünse de,
// ikinci şeklin görünen dış sınırları gölge ve anahattan etkilenir ve bu nedenle daha büyüktür.
// Şeklin gerçek boyutunu görmek için "AdjustWithEffects" yöntemini kullanabiliriz.
Assert.AreEqual(0.0, shapes[0].StrokeWeight);
Assert.AreEqual(20.0, shapes[1].StrokeWeight);
Assert.False(shapes[0].ShadowEnabled);
Assert.True(shapes[1].ShadowEnabled);

Shape shape = shapes[0];

// Bir dikdörtgeni temsil eden bir RectangleF nesnesi oluşturun,
// potansiyel olarak bir şeklin koordinatları ve sınırları olarak kullanabileceğimiz.
RectangleF rectangleF = new RectangleF(200, 200, 1000, 1000);

// Tüm şekil efektlerimiz için ayarlanmış dikdörtgenin boyutunu elde etmek için bu yöntemi çalıştırın.
RectangleF rectangleFOut = shape.AdjustWithEffects(rectangleF);

// Şeklin kenar değiştirme etkisi olmadığı için sınır boyutları etkilenmez.
Assert.AreEqual(200, rectangleFOut.X);
Assert.AreEqual(200, rectangleFOut.Y);
Assert.AreEqual(1000, rectangleFOut.Width);
Assert.AreEqual(1000, rectangleFOut.Height);

// İlk şeklin son kapsamını nokta olarak doğrulayın.
Assert.AreEqual(0, shape.BoundsWithEffects.X);
Assert.AreEqual(0, shape.BoundsWithEffects.Y);
Assert.AreEqual(147, shape.BoundsWithEffects.Width);
Assert.AreEqual(147, shape.BoundsWithEffects.Height);

shape = shapes[1];
rectangleF = new RectangleF(200, 200, 1000, 1000);
rectangleFOut = shape.AdjustWithEffects(rectangleF);

// Şekil efektleri, şeklin görünen sol üst köşesini biraz hareket ettirdi.
Assert.AreEqual(171.5, rectangleFOut.X);
Assert.AreEqual(167, rectangleFOut.Y);

// Efektler, şeklin görünür boyutlarını da etkiledi.
Assert.AreEqual(1045, rectangleFOut.Width);
Assert.AreEqual(1132, rectangleFOut.Height);

// Efektler, şeklin görünür sınırlarını da etkiledi.
Assert.AreEqual(-28.5, shape.BoundsWithEffects.X);
Assert.AreEqual(-33, shape.BoundsWithEffects.Y);
Assert.AreEqual(192, shape.BoundsWithEffects.Width);
Assert.AreEqual(279, shape.BoundsWithEffects.Height);
```

### Ayrıca bakınız

* class [ShapeBase](../)
* ad alanı [Aspose.Words.Drawing](../../shapebase/)
* toplantı [Aspose.Words](../../../)


