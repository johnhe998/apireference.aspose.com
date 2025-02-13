---
title: DocumentBase.BackgroundShape
second_title: Aspose.Words for .NET API Referansı
description: DocumentBase mülk. Belgenin arka plan şeklini alır veya ayarlar. null. olabilir
type: docs
weight: 10
url: /tr/net/aspose.words/documentbase/backgroundshape/
---
## DocumentBase.BackgroundShape property

Belgenin arka plan şeklini alır veya ayarlar. null. olabilir

```csharp
public Shape BackgroundShape { get; set; }
```

### Notlar

Microsoft Word, yalnızca kendi biçimine sahip bir şekle izin verir.[`ShapeType`](../../../aspose.words.drawing/shapebase/shapetype/) özellik ile eşittirRectangle bir belge için arka plan şekli olarak kullanılmak üzere.

Microsoft Word, yalnızca bir arka plan şeklinin dolgu özelliklerini destekler. Diğer tüm özellikler yoksayılır.

Bu özelliği boş olmayan bir değere ayarlamak, aynı zamanda[`DisplayBackgroundShape`](../../../aspose.words.settings/viewoptions/displaybackgroundshape/) doğru.

### Örnekler

Bir belgenin her sayfası için nasıl arka plan şekli ayarlanacağını gösterir.

```csharp
Document doc = new Document();

Assert.IsNull(doc.BackgroundShape);

// Arka plan olarak kullanabileceğimiz tek şekil türü dikdörtgendir.
Shape shapeRectangle = new Shape(doc, ShapeType.Rectangle);

// Bu şekli sayfa arka planı olarak kullanmanın iki yolu vardır.
// 1 - Düz bir renk:
shapeRectangle.FillColor = System.Drawing.Color.LightBlue;
doc.BackgroundShape = shapeRectangle;

doc.Save(ArtifactsDir + "DocumentBase.BackgroundShape.FlatColor.docx");

// 2 - Bir resim:
shapeRectangle = new Shape(doc, ShapeType.Rectangle);
shapeRectangle.ImageData.SetImage(ImageDir + "Transparent background logo.png");

// Filigran olarak daha uygun hale getirmek için görüntünün görünümünü ayarlayın.
shapeRectangle.ImageData.Contrast = 0.2;
shapeRectangle.ImageData.Brightness = 0.7;

doc.BackgroundShape = shapeRectangle;

Assert.IsTrue(doc.BackgroundShape.HasImage);

// Microsoft Word, arka planda resim bulunan şekilleri desteklemez,
// ama yine de bu arka planları .pdf gibi diğer kaydetme biçimlerinde görebiliriz.
doc.Save(ArtifactsDir + "DocumentBase.BackgroundShape.Image.pdf");
```

### Ayrıca bakınız

* class [Shape](../../../aspose.words.drawing/shape/)
* class [DocumentBase](../)
* ad alanı [Aspose.Words](../../documentbase/)
* toplantı [Aspose.Words](../../../)


