---
title: Enum ShapeLineStyle
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Drawing.ShapeLineStyle Sıralama. Bir dizinin bileşik çizgi stilini belirtir.Shape .
type: docs
weight: 1120
url: /tr/net/aspose.words.drawing/shapelinestyle/
---
## ShapeLineStyle enumeration

Bir dizinin bileşik çizgi stilini belirtir.[`Shape`](../shape/) .

```csharp
public enum ShapeLineStyle
```

### değerler

| İsim | Değer | Tanım |
| --- | --- | --- |
| Single | `0` | Tek satır. |
| Double | `1` | Eşit genişlikte çift satır. |
| ThickThin | `2` | Çift çizgiler, biri kalın, biri ince. |
| ThinThick | `3` | Çift çizgiler, biri ince, biri kalın. |
| Triple | `4` | Üç çizgi, ince, kalın, ince. |
| Default | `0` | Varsayılan değerSingle . |

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

* property [LineStyle](../stroke/linestyle/)
* ad alanı [Aspose.Words.Drawing](../../aspose.words.drawing/)
* toplantı [Aspose.Words](../../)


