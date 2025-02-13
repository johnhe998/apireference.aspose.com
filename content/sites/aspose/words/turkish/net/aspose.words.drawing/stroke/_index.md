---
title: Class Stroke
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Drawing.Stroke sınıf. Bir şekil için kontur tanımlar.
type: docs
weight: 1160
url: /tr/net/aspose.words.drawing/stroke/
---
## Stroke class

Bir şekil için kontur tanımlar.

```csharp
public class Stroke
```

## Özellikleri

| İsim | Tanım |
| --- | --- |
| [BackColor](../../aspose.words.drawing/stroke/backcolor/) { get; set; } | Konturun arka plan rengini alır veya ayarlar. |
| [Color](../../aspose.words.drawing/stroke/color/) { get; set; } | Konturun rengini tanımlar. |
| [Color2](../../aspose.words.drawing/stroke/color2/) { get; set; } | Kontur için ikinci bir renk tanımlar. |
| [DashStyle](../../aspose.words.drawing/stroke/dashstyle/) { get; set; } | Bir kontur için nokta ve çizgi desenini belirtir. |
| [EndArrowLength](../../aspose.words.drawing/stroke/endarrowlength/) { get; set; } | Bir konturun sonu için ok ucu uzunluğunu tanımlar. |
| [EndArrowType](../../aspose.words.drawing/stroke/endarrowtype/) { get; set; } | Konturun sonu için ok ucunu tanımlar. |
| [EndArrowWidth](../../aspose.words.drawing/stroke/endarrowwidth/) { get; set; } | Konturun sonu için ok ucu genişliğini tanımlar. |
| [EndCap](../../aspose.words.drawing/stroke/endcap/) { get; set; } | Kontur sonu için başlık stilini tanımlar. |
| [ForeColor](../../aspose.words.drawing/stroke/forecolor/) { get; set; } | Konturun ön plan rengini alır veya ayarlar. |
| [ImageBytes](../../aspose.words.drawing/stroke/imagebytes/) { get; } | Kontur görüntüsü veya desen dolgusu için görüntüyü tanımlar. |
| [JoinStyle](../../aspose.words.drawing/stroke/joinstyle/) { get; set; } | Bir çoklu çizginin birleştirme stilini tanımlar. |
| [LineStyle](../../aspose.words.drawing/stroke/linestyle/) { get; set; } | Konturun çizgi stilini tanımlar. |
| [On](../../aspose.words.drawing/stroke/on/) { get; set; } | Yolun konturlu olup olmayacağını tanımlar. |
| [Opacity](../../aspose.words.drawing/stroke/opacity/) { get; set; } | Bir konturun şeffaflık miktarını tanımlar. Geçerli aralık 0 ile 1. arasındadır |
| [StartArrowLength](../../aspose.words.drawing/stroke/startarrowlength/) { get; set; } | Bir vuruşun başlangıcı için ok ucu uzunluğunu tanımlar. |
| [StartArrowType](../../aspose.words.drawing/stroke/startarrowtype/) { get; set; } | Bir vuruşun başlangıcı için ok ucunu tanımlar. |
| [StartArrowWidth](../../aspose.words.drawing/stroke/startarrowwidth/) { get; set; } | Kontur başlangıcı için ok ucu genişliğini tanımlar. |
| [Transparency](../../aspose.words.drawing/stroke/transparency/) { get; set; } | Konturun şeffaflık derecesini temsil eden 0.0 (opak) ile 1.0 (net) arasında bir değer alır veya ayarlar. |
| [Visible](../../aspose.words.drawing/stroke/visible/) { get; set; } | Konturun görünür olup olmadığını belirten bir bayrak alır veya ayarlar. |
| [Weight](../../aspose.words.drawing/stroke/weight/) { get; set; } | Bir şeklin yolunu nokta olarak çizen fırça kalınlığını tanımlar. |

### Notlar

Kullan[`Stroke`](../shape/stroke/)bir şeklin kontur özelliklerine erişme özelliği. `Stroke` doğrudan sınıf.

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

* ad alanı [Aspose.Words.Drawing](../../aspose.words.drawing/)
* toplantı [Aspose.Words](../../)


