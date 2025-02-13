---
title: ShapeBase.BoundsInPoints
second_title: Aspose.Words for .NET API Referansı
description: ShapeBase mülk. En üstteki şeklin bağlantısına göre şekli içeren bloğun konumunu ve boyutunu nokta olarak alır.
type: docs
weight: 80
url: /tr/net/aspose.words.drawing/shapebase/boundsinpoints/
---
## ShapeBase.BoundsInPoints property

En üstteki şeklin bağlantısına göre, şekli içeren bloğun konumunu ve boyutunu nokta olarak alır.

```csharp
public RectangleF BoundsInPoints { get; }
```

### Örnekler

Blok sınırlarını içeren şeklin nasıl doğrulanacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertShape(ShapeType.Line, RelativeHorizontalPosition.LeftMargin, 50,
    RelativeVerticalPosition.TopMargin, 50, 100, 100, WrapType.None);
shape.StrokeColor = Color.Orange;

// Satırın kendisi belge sayfasında çok az yer kaplasa da,
// boyutunu "Sınırlar" özelliklerini kullanarak belirleyebileceğimiz dikdörtgen içeren bir blok kaplar.
Assert.AreEqual(new RectangleF(50, 50, 100, 100), shape.Bounds);
Assert.AreEqual(new RectangleF(50, 50, 100, 100), shape.BoundsInPoints);

// Bir grup şekli oluşturun ve ardından "Sınırlar" özelliğini kullanarak içerdiği bloğun boyutunu ayarlayın.
GroupShape group = new GroupShape(doc);
group.Bounds = new RectangleF(0, 100, 250, 250);

Assert.AreEqual(new RectangleF(0, 100, 250, 250), group.BoundsInPoints);

// Bir dikdörtgen oluşturun, sınırlayıcı bloğunun boyutunu doğrulayın ve ardından onu grup şekline ekleyin.
shape = new Shape(doc, ShapeType.Rectangle)
{
    Width = 100,
    Height = 100,
    Left = 700,
    Top = 700
};

Assert.AreEqual(new RectangleF(700, 700, 100, 100), shape.BoundsInPoints);

group.AppendChild(shape);

// Grup şeklinin koordinat düzleminin başlangıç noktası, içerdiği bloğun sol üst köşesindedir,
// ve sağ alt köşede (1000, 1000) x ve y koordinatları.
// Grup şeklimiz 250x250pt boyutundadır, yani grup şeklinin koordinat düzlemindeki her 4pt
// belge gövdesinin koordinat düzleminde 1pt'ye çevirir.
// Eklediğimiz her şeklin boyutu da 4 kat küçülecek.
// Şeklin "BoundsInPoints" özelliğindeki değişiklik bunu yansıtacaktır.
Assert.AreEqual(new RectangleF(175, 275, 25, 25), shape.BoundsInPoints);

doc.FirstSection.Body.FirstParagraph.AppendChild(group);

// Bir şekil ekleyin ve onu grup şeklinin içeren bloğunun sınırlarının dışına yerleştirin.
shape = new Shape(doc, ShapeType.Rectangle)
{
    Width = 100,
    Height = 100,
    Left = 1000,
    Top = 1000
};

group.AppendChild(shape);

// Grup şeklinin belge gövdesindeki ayak izi arttı, ancak içeren blok aynı kaldı.
Assert.AreEqual(new RectangleF(0, 100, 250, 250), group.BoundsInPoints);
Assert.AreEqual(new RectangleF(250, 350, 25, 25), shape.BoundsInPoints);

doc.Save(ArtifactsDir + "Shape.Bounds.docx");
```

### Ayrıca bakınız

* class [ShapeBase](../)
* ad alanı [Aspose.Words.Drawing](../../shapebase/)
* toplantı [Aspose.Words](../../../)


