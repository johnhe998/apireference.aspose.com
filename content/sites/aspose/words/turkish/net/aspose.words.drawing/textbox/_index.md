---
title: Class TextBox
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Drawing.TextBox sınıf. Bir metnin bir şeklin içinde nasıl görüntüleneceğini belirten nitelikleri tanımlar.
type: docs
weight: 1170
url: /tr/net/aspose.words.drawing/textbox/
---
## TextBox class

Bir metnin bir şeklin içinde nasıl görüntüleneceğini belirten nitelikleri tanımlar.

```csharp
public class TextBox
```

## Özellikleri

| İsim | Tanım |
| --- | --- |
| [FitShapeToText](../../aspose.words.drawing/textbox/fitshapetotext/) { get; set; } | Microsoft Word'ün şekli metne sığdırmak için büyütüp büyütmeyeceğini belirler. |
| [InternalMarginBottom](../../aspose.words.drawing/textbox/internalmarginbottom/) { get; set; } | Bir şeklin iç alt kenar boşluğunu nokta olarak belirtir. |
| [InternalMarginLeft](../../aspose.words.drawing/textbox/internalmarginleft/) { get; set; } | Bir şeklin sol iç kenar boşluğunu nokta olarak belirtir. |
| [InternalMarginRight](../../aspose.words.drawing/textbox/internalmarginright/) { get; set; } | Bir şeklin sağ iç kenar boşluğunu nokta olarak belirtir. |
| [InternalMarginTop](../../aspose.words.drawing/textbox/internalmargintop/) { get; set; } | Bir şeklin iç üst kenar boşluğunu nokta olarak belirtir. |
| [LayoutFlow](../../aspose.words.drawing/textbox/layoutflow/) { get; set; } | Bir şekildeki metin düzeninin akışını belirler. |
| [Next](../../aspose.words.drawing/textbox/next/) { get; set; } | Bir dizi şekil içinde sonraki Metin Kutusunu temsil eden bir Metin Kutusunu döndürür veya ayarlar. |
| [Parent](../../aspose.words.drawing/textbox/parent/) { get; } | TextBox için bir üst şekil alır. |
| [Previous](../../aspose.words.drawing/textbox/previous/) { get; } | Bir dizi şekil içinde önceki Metin Kutusunu temsil eden bir Metin Kutusu döndürür. |
| [TextBoxWrapMode](../../aspose.words.drawing/textbox/textboxwrapmode/) { get; set; } | Metnin bir şeklin içine nasıl kaydırılacağını belirler. |
| [VerticalAnchor](../../aspose.words.drawing/textbox/verticalanchor/) { get; set; } | Bir şekil içindeki metnin dikey hizalamasını belirtir. |

## yöntemler

| İsim | Tanım |
| --- | --- |
| [BreakForwardLink](../../aspose.words.drawing/textbox/breakforwardlink/)() | Sonraki TextBox'a olan bağlantıyı keser. |
| [IsValidLinkTarget](../../aspose.words.drawing/textbox/isvalidlinktarget/)(TextBox) | Bu Metin Kutusunun hedef Metin Kutusuna bağlanıp bağlanamayacağını belirler. |

### Notlar

Kullan[`TextBox`](../shape/textbox/) bir şeklin metin özelliklerine erişme özelliği. `TextBox` doğrudan sınıf.

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

Bir metin kutusu içindeki metnin yönünün nasıl ayarlanacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape textBoxShape = builder.InsertShape(ShapeType.TextBox, 150, 100);
TextBox textBox = textBoxShape.TextBox;

// Belge oluşturucuyu TextBox'ın içine taşıyın ve metin ekleyin.
builder.MoveTo(textBoxShape.LastParagraph);
builder.Writeln("Hello world!");
builder.Write("Hello again!");

// Bu metin kutusunun metin içeriği için bir yönlendirme ayarlamak için "LayoutFlow" özelliğini ayarlayın.
textBox.LayoutFlow = layoutFlow;

doc.Save(ArtifactsDir + "Shape.TextBoxLayoutFlow.docx");
```

İçeriğini sıkıca sığdırmak için kendisini yeniden boyutlandırmak için bir metin kutusunun nasıl alınacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape textBoxShape = builder.InsertShape(ShapeType.TextBox, 150, 100);
TextBox textBox = textBoxShape.TextBox;

// Üst şeklin sığdırılması için bu değerleri her iki üyeye de uygulayın
// belirlediğimiz boyutları göz ardı ederek metin içeriklerinin etrafını sıkıca sarıyoruz.
textBox.FitShapeToText = true;
textBox.TextBoxWrapMode = TextBoxWrapMode.None;

builder.MoveTo(textBoxShape.LastParagraph);
builder.Write("Text fit tightly inside textbox.");

doc.Save(ArtifactsDir + "Shape.TextBoxFitShapeToText.docx");
```

### Ayrıca bakınız

* ad alanı [Aspose.Words.Drawing](../../aspose.words.drawing/)
* toplantı [Aspose.Words](../../)


