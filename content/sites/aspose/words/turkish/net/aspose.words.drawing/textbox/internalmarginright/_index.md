---
title: TextBox.InternalMarginRight
second_title: Aspose.Words for .NET API Referansı
description: TextBox mülk. Bir şeklin sağ iç kenar boşluğunu nokta olarak belirtir.
type: docs
weight: 40
url: /tr/net/aspose.words.drawing/textbox/internalmarginright/
---
## TextBox.InternalMarginRight property

Bir şeklin sağ iç kenar boşluğunu nokta olarak belirtir.

```csharp
public double InternalMarginRight { get; set; }
```

### Notlar

Varsayılan değer 1/10 inçtir.

### Örnekler

Bir metin kutusu için iç kenar boşluklarının nasıl ayarlanacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Belirli kenar boşluklarına sahip başka bir metin kutusu ekleyin.
Shape textBoxShape = builder.InsertShape(ShapeType.TextBox, 100, 100);
TextBox textBox = textBoxShape.TextBox;
textBox.InternalMarginTop = 15;
textBox.InternalMarginBottom = 15;
textBox.InternalMarginLeft = 15;
textBox.InternalMarginRight = 15;

builder.MoveTo(textBoxShape.LastParagraph);
builder.Write("Text placed according to textbox margins.");

doc.Save(ArtifactsDir + "Shape.TextBoxMargins.docx");
```

### Ayrıca bakınız

* class [TextBox](../)
* ad alanı [Aspose.Words.Drawing](../../textbox/)
* toplantı [Aspose.Words](../../../)


