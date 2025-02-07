---
title: Class GradientStopCollection
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Drawing.GradientStopCollection sınıf. Bir koleksiyon içerirGradientStop nesneler.
type: docs
weight: 860
url: /tr/net/aspose.words.drawing/gradientstopcollection/
---
## GradientStopCollection class

Bir koleksiyon içerir[`GradientStop`](../gradientstop/) nesneler.

```csharp
public class GradientStopCollection : IEnumerable<GradientStop>
```

## Özellikleri

| İsim | Tanım |
| --- | --- |
| [Count](../../aspose.words.drawing/gradientstopcollection/count/) { get; } | Koleksiyondaki öğelerin sayısını gösteren bir tamsayı değeri alır. |
| [Item](../../aspose.words.drawing/gradientstopcollection/item/) { get; set; } | Alır veya ayarlar[`GradientStop`](../gradientstop/) koleksiyondaki nesne. |

## yöntemler

| İsim | Tanım |
| --- | --- |
| [Add](../../aspose.words.drawing/gradientstopcollection/add/)(GradientStop) | Belirtilen ekler[`GradientStop`](../gradientstop/) bir degradeye. |
| [GetEnumerator](../../aspose.words.drawing/gradientstopcollection/getenumerator/)() | Koleksiyon boyunca yinelenen bir Numaralandırıcı döndürür. |
| [Insert](../../aspose.words.drawing/gradientstopcollection/insert/)(int, GradientStop) | Bir ekler[`GradientStop`](../gradientstop/) belirli bir dizindeki koleksiyona. |
| [Remove](../../aspose.words.drawing/gradientstopcollection/remove/)(GradientStop) | Belirtilen bir öğeyi kaldırır[`GradientStop`](../gradientstop/) koleksiyondan. |
| [RemoveAt](../../aspose.words.drawing/gradientstopcollection/removeat/)(int) | Bir[`GradientStop`](../gradientstop/)belirli bir dizindeki koleksiyondan. |

### Notlar

Bu sınıfın örneklerini doğrudan oluşturmazsınız. [`GradientStops`](../fill/gradientstops/) dolgu nesnelerinin gradyan duraklarına erişme özelliği.

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

* class [GradientStop](../gradientstop/)
* ad alanı [Aspose.Words.Drawing](../../aspose.words.drawing/)
* toplantı [Aspose.Words](../../)


