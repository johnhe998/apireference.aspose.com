---
title: TextBox.IsValidLinkTarget
second_title: Aspose.Words for .NET API Referansı
description: TextBox yöntem. Bu Metin Kutusunun hedef Metin Kutusuna bağlanıp bağlanamayacağını belirler.
type: docs
weight: 130
url: /tr/net/aspose.words.drawing/textbox/isvalidlinktarget/
---
## TextBox.IsValidLinkTarget method

Bu Metin Kutusunun hedef Metin Kutusuna bağlanıp bağlanamayacağını belirler.

```csharp
public bool IsValidLinkTarget(TextBox target)
```

### Örnekler

Metin kutularının nasıl bağlanacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape textBoxShape1 = builder.InsertShape(ShapeType.TextBox, 100, 100);
TextBox textBox1 = textBoxShape1.TextBox;
builder.Writeln();

Shape textBoxShape2 = builder.InsertShape(ShapeType.TextBox, 100, 100);
TextBox textBox2 = textBoxShape2.TextBox;
builder.Writeln();

Shape textBoxShape3 = builder.InsertShape(ShapeType.TextBox, 100, 100);
TextBox textBox3 = textBoxShape3.TextBox;
builder.Writeln();

Shape textBoxShape4 = builder.InsertShape(ShapeType.TextBox, 100, 100);
TextBox textBox4 = textBoxShape4.TextBox;

// Bazı metin kutuları arasında bağlantılar oluşturun.
if (textBox1.IsValidLinkTarget(textBox2))
    textBox1.Next = textBox2;

if (textBox2.IsValidLinkTarget(textBox3))
    textBox2.Next = textBox3;

// Yalnızca boş bir metin kutusunda bir bağlantı olabilir.
Assert.True(textBox3.IsValidLinkTarget(textBox4));

builder.MoveTo(textBoxShape4.LastParagraph);
builder.Write("Hello world!");

Assert.False(textBox3.IsValidLinkTarget(textBox4));

if (textBox1.Next != null && textBox1.Previous == null)
    Console.WriteLine("This TextBox is the head of the sequence");

if (textBox2.Next != null && textBox2.Previous != null)
    Console.WriteLine("This TextBox is the middle of the sequence");

if (textBox3.Next == null && textBox3.Previous != null)
{
    Console.WriteLine("This TextBox is the tail of the sequence");

    // textBox2 ve textBox3 arasındaki yönlendirme bağlantısını kesin ve ardından artık bağlantılı olmadıklarını doğrulayın.
    textBox3.Previous.BreakForwardLink();

    Assert.IsTrue(textBox2.Next == null);
    Assert.IsTrue(textBox3.Previous == null);
}

doc.Save(ArtifactsDir + "Shape.CreateLinkBetweenTextBoxes.docx");
```

### Ayrıca bakınız

* class [TextBox](../)
* ad alanı [Aspose.Words.Drawing](../../textbox/)
* toplantı [Aspose.Words](../../../)


