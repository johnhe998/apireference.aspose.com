---
title: ShapeBase.Font
second_title: Aspose.Words for .NET API Referansı
description: ShapeBase mülk. Bu nesnenin yazı tipi biçimlendirmesine erişim sağlar.
type: docs
weight: 190
url: /tr/net/aspose.words.drawing/shapebase/font/
---
## ShapeBase.Font property

Bu nesnenin yazı tipi biçimlendirmesine erişim sağlar.

```csharp
public Font Font { get; }
```

### Örnekler

Metin kutusunun nasıl ekleneceğini ve içeriğinin yazı tipinin nasıl ayarlanacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Hello world!");

Shape shape = builder.InsertShape(ShapeType.TextBox, 300, 50);
builder.MoveTo(shape.LastParagraph);
builder.Write("This text is inside the text box.");

// Metin kutusunu görünmez kılmak için şeklin "Font" nesnesinin "Gizli" özelliğini "true" olarak ayarlayın
// ve normalde kaplayacağı alanı daraltın.
// Metin kutusunu görünür bırakmak için şeklin "Font" nesnesinin "Gizli" özelliğini "false" olarak ayarlayın.
shape.Font.Hidden = hideShape;

// Şekil görünürse, yazı tipi nesnesi aracılığıyla görünümünü değiştireceğiz.
if (!hideShape)
{
    shape.Font.HighlightColor = Color.LightGray;
    shape.Font.Color = Color.Red;
    shape.Font.Underline = Underline.Dash;
}

// Oluşturucuyu metin kutusundan ana belgeye geri taşıyın.
builder.MoveTo(shape.ParentParagraph);

builder.Writeln("\nThis text is outside the text box.");

doc.Save(ArtifactsDir + "Shape.Font.docx");
```

### Ayrıca bakınız

* class [Font](../../../aspose.words/font/)
* class [ShapeBase](../)
* ad alanı [Aspose.Words.Drawing](../../shapebase/)
* toplantı [Aspose.Words](../../../)


