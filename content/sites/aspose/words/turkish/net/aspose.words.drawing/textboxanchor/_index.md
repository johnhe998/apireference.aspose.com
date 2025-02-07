---
title: Enum TextBoxAnchor
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Drawing.TextBoxAnchor Sıralama. Şekil metni dikey hizalaması için kullanılan değerleri belirtir.
type: docs
weight: 1180
url: /tr/net/aspose.words.drawing/textboxanchor/
---
## TextBoxAnchor enumeration

Şekil metni dikey hizalaması için kullanılan değerleri belirtir.

```csharp
public enum TextBoxAnchor
```

### değerler

| İsim | Değer | Tanım |
| --- | --- | --- |
| Top | `0` | Metin, metin kutusunun üstüne hizalanır. |
| Middle | `1` | Metin, metin kutusunun ortasına hizalanır. |
| Bottom | `2` | Metin, metin kutusunun altına hizalanır. |
| TopCentered | `3` | Metin, metin kutusunun üst ortasına hizalanır. |
| MiddleCentered | `4` | Metin, metin kutusunun ortasına hizalanır. |
| BottomCentered | `5` | Metin, metin kutusunun alt orta kısmına hizalanır. |
| TopBaseline | `6` | Metin, metin kutusunun üst satır taban çizgisine hizalanır. |
| BottomBaseline | `7` | Metin, metin kutusunun alt satır taban çizgisine hizalanır. |
| TopCenteredBaseline | `8` | Metin, metin kutusunun üst ortalanmış satır taban çizgisine hizalanır. |
| BottomCenteredBaseline | `9` | Metin, metin kutusunun alt orta satır taban çizgisine hizalanır. |

### Örnekler

Bir metin kutusunun metin içeriğinin dikey olarak nasıl hizalanacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertShape(ShapeType.TextBox, 200, 200);

// "VerticalAnchor" özelliğini "TextBoxAnchor.Top" olarak ayarlayın.
// bu metin kutusundaki metni şeklin üst tarafıyla hizalayın.
// "VerticalAnchor" özelliğini "TextBoxAnchor.Middle" olarak ayarlayın.
// bu metin kutusundaki metni şeklin ortasına hizalayın.
// "VerticalAnchor" özelliğini "TextBoxAnchor.Bottom" olarak ayarlayın.
// bu metin kutusundaki metni şeklin altına hizalayın.
shape.TextBox.VerticalAnchor = verticalAnchor;

builder.MoveTo(shape.FirstParagraph);
builder.Write("Hello world!");

// Metin kutularının içindeki metnin dikey olarak hizalanması, Microsoft Word 2007'den itibaren mevcuttur.
doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2007);
doc.Save(ArtifactsDir + "Shape.VerticalAnchor.docx");
```

### Ayrıca bakınız

* ad alanı [Aspose.Words.Drawing](../../aspose.words.drawing/)
* toplantı [Aspose.Words](../../)


