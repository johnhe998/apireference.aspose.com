---
title: ShapeBase.IsDecorative
second_title: Aspose.Words for .NET API Referansı
description: ShapeBase mülk. Şeklin belgede dekoratif olup olmadığını belirten bayrağı alır veya ayarlar.
type: docs
weight: 230
url: /tr/net/aspose.words.drawing/shapebase/isdecorative/
---
## ShapeBase.IsDecorative property

Şeklin belgede dekoratif olup olmadığını belirten bayrağı alır veya ayarlar.

```csharp
public bool IsDecorative { get; set; }
```

### Notlar

Şeklin boş olmadığına dikkat edin[`AlternativeText`](../alternativetext/) dekoratif olamaz.

### Örnekler

Şeklin dekoratif olduğunun nasıl ayarlanacağını gösterir.

```csharp
Document doc = new Document(MyDir + "Decorative shapes.docx");

Shape shape = (Shape) doc.GetChildNodes(NodeType.Shape, true)[0];
Assert.True(shape.IsDecorative);

// "AlternativeText" boş değilse şekil dekoratif olamaz.
// Bu yüzden değerimiz 'false' olarak değişti.
shape.AlternativeText = "Alternative text.";
Assert.False(shape.IsDecorative);

DocumentBuilder builder = new DocumentBuilder(doc);

builder.MoveToDocumentEnd();
// Dekoratif olarak yeni bir şekil oluşturun.
shape = builder.InsertShape(ShapeType.Rectangle, 100, 100);
shape.IsDecorative = true;

doc.Save(ArtifactsDir + "Shape.IsDecorative.docx");
```

### Ayrıca bakınız

* class [ShapeBase](../)
* ad alanı [Aspose.Words.Drawing](../../shapebase/)
* toplantı [Aspose.Words](../../../)


