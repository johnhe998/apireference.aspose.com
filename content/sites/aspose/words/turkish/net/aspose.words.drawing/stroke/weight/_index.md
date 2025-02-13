---
title: Stroke.Weight
second_title: Aspose.Words for .NET API Referansı
description: Stroke mülk. Bir şeklin yolunu nokta olarak çizen fırça kalınlığını tanımlar.
type: docs
weight: 200
url: /tr/net/aspose.words.drawing/stroke/weight/
---
## Stroke.Weight property

Bir şeklin yolunu nokta olarak çizen fırça kalınlığını tanımlar.

```csharp
public double Weight { get; set; }
```

### Notlar

Bir için varsayılan değer[`Shape`](../../shape/) 0.75'tir.

### Örnekler

Kontur özelliklerinin nasıl değiştirildiğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertShape(ShapeType.Rectangle, RelativeHorizontalPosition.LeftMargin, 100,
    RelativeVerticalPosition.TopMargin, 100, 200, 200, WrapType.None);

// Dikdörtgen gibi temel şekillerin iki görünür parçası vardır.
// 1 - Şeklin anahattı içindeki alana uygulanan dolgu:
shape.Fill.ForeColor = Color.White;

// 2 - Şeklin ana hatlarını belirleyen kontur:
// Bu şeklin konturunun çeşitli özelliklerini değiştirin.
Stroke stroke = shape.Stroke;
stroke.On = true;
stroke.Weight = 5;
stroke.Color = Color.Red;
stroke.DashStyle = DashStyle.ShortDashDotDot;
stroke.JoinStyle = JoinStyle.Miter;
stroke.EndCap = EndCap.Square;
stroke.LineStyle = ShapeLineStyle.Triple;

doc.Save(ArtifactsDir + "Shape.Stroke.docx");
```

### Ayrıca bakınız

* class [Stroke](../)
* ad alanı [Aspose.Words.Drawing](../../stroke/)
* toplantı [Aspose.Words](../../../)


