---
title: TextBox.TextBoxWrapMode
second_title: Aspose.Words for .NET API Referansı
description: TextBox mülk. Metnin bir şeklin içine nasıl kaydırılacağını belirler.
type: docs
weight: 100
url: /tr/net/aspose.words.drawing/textbox/textboxwrapmode/
---
## TextBox.TextBoxWrapMode property

Metnin bir şeklin içine nasıl kaydırılacağını belirler.

```csharp
public TextBoxWrapMode TextBoxWrapMode { get; set; }
```

### Notlar

Varsayılan değerSquare.

### Örnekler

Bir metin kutusunun içeriği için bir kaydırma modunun nasıl ayarlanacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape textBoxShape = builder.InsertShape(ShapeType.TextBox, 300, 300);
TextBox textBox = textBoxShape.TextBox;

// Metin kutusunun genişliğini artırmak için "TextBoxWrapMode" özelliğini "TextBoxWrapMode.None" olarak ayarlayın
// metni yerleştirmek için, yeterince büyük olması gerekir.
// "TextBoxWrapMode" özelliğini "TextBoxWrapMode.Square" olarak ayarlayın.
// tüm metni boyutlarını koruyarak metin kutusunun içine sarın.
textBox.TextBoxWrapMode = textBoxWrapMode;

builder.MoveTo(textBoxShape.LastParagraph);
builder.Font.Size = 32;
builder.Write("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");

doc.Save(ArtifactsDir + "Shape.TextBoxContentsWrapMode.docx");
```

### Ayrıca bakınız

* enum [TextBoxWrapMode](../../textboxwrapmode/)
* class [TextBox](../)
* ad alanı [Aspose.Words.Drawing](../../textbox/)
* toplantı [Aspose.Words](../../../)


