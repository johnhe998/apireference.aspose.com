---
title: GradientStop.Transparency
second_title: Aspose.Words for .NET API Referansı
description: GradientStop mülk. 0.0 ila 1.0. aralığında yüzde olarak ifade edilen fill degradesinin şeffaflığını temsil eden bir değer alır veya ayarlar
type: docs
weight: 40
url: /tr/net/aspose.words.drawing/gradientstop/transparency/
---
## GradientStop.Transparency property

0.0 ila 1.0. aralığında yüzde olarak ifade edilen fill degradesinin şeffaflığını temsil eden bir değer alır veya ayarlar

```csharp
public double Transparency { get; set; }
```

### Örnekler

Degrade dolguya degrade duraklarının nasıl ekleneceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertShape(ShapeType.Rectangle, 80, 80);
shape.Fill.TwoColorGradient(Color.Green, Color.Red, GradientStyle.Horizontal, GradientVariant.Variant2);

// Degrade durak koleksiyonunu alın.
GradientStopCollection gradientStops = shape.Fill.GradientStops;

// İlk degrade durağını değiştir.
gradientStops[0].Color = Color.Aqua;
gradientStops[0].Position = 0.1;
gradientStops[0].Transparency = 0.25;

// Koleksiyonun sonuna yeni degrade durağı ekleyin.
GradientStop gradientStop = new GradientStop(Color.Brown, 0.5);
gradientStops.Add(gradientStop);

// Dizin 1'deki degrade durağını kaldırın.
gradientStops.RemoveAt(1);
// Ve aynı indeks 1'e yeni degrade durağı ekleyin.
gradientStops.Insert(1, new GradientStop(Color.Chocolate, 0.75, 0.3));

// Koleksiyondaki son degrade durağını kaldırın.
gradientStop = gradientStops[2];
gradientStops.Remove(gradientStop);

Assert.AreEqual(2, gradientStops.Count);

Assert.AreEqual(Color.Aqua.ToArgb(), gradientStops[0].Color.ToArgb());
Assert.AreEqual(0.1d, gradientStops[0].Position, 0.01d);
Assert.AreEqual(0.25d, gradientStops[0].Transparency, 0.01d);

Assert.AreEqual(Color.Chocolate.ToArgb(), gradientStops[1].Color.ToArgb());
Assert.AreEqual(0.75d, gradientStops[1].Position, 0.01d);
Assert.AreEqual(0.3d, gradientStops[1].Transparency, 0.01d);

// DML kullanarak şekli tanımlamak için uyumluluk seçeneğini kullanın
// Belge kaydedildikten sonra "GradientStops" özelliğini almak istiyorsanız.
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Strict };

doc.Save(ArtifactsDir + "Shape.GradientStops.docx", saveOptions);
```

### Ayrıca bakınız

* class [GradientStop](../)
* ad alanı [Aspose.Words.Drawing](../../gradientstop/)
* toplantı [Aspose.Words](../../../)


