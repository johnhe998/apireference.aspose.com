---
title: EndnoteOptions.Position
second_title: Aspose.Words for .NET API Referansı
description: EndnoteOptions mülk. Son notların konumunu belirtir.
type: docs
weight: 20
url: /tr/net/aspose.words.notes/endnoteoptions/position/
---
## EndnoteOptions.Position property

Son notların konumunu belirtir.

```csharp
public EndnotePosition Position { get; set; }
```

### Örnekler

Belgenin son notlarını topladığı ve görüntülediği farklı bir yerin nasıl seçileceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Son not, metne referans veya yan yorum eklemenin bir yoludur
// ana gövde metninin akışını engellemez. 
// Bir son not eklemek, küçük bir üst simge referans sembolü ekler
// son notu eklediğimiz ana gövde metninde.
// Her son not ayrıca belgenin sonunda bir sembolden oluşan bir giriş oluşturur.
// ana gövde metnindeki referans sembolüyle eşleşen.
// Belge oluşturucunun "InsertEndnote" yöntemine aktardığımız referans metni.
builder.Write("Hello world!");
builder.InsertFootnote(FootnoteType.Endnote, "Endnote contents.");
builder.InsertBreak(BreakType.SectionBreakNewPage);
builder.Write("This is the second section.");

// Belgenin tüm son notlarını nereye yerleştireceğini belirlemek için "Position" özelliğini kullanabiliriz.
// "Position" özelliğinin değerini "EndnotePosition.EndOfDocument" olarak ayarlarsak,
// her dipnot belgenin sonunda bir koleksiyonda görünecek. Bu varsayılan değerdir.
// "Position" özelliğinin değerini "EndnotePosition.EndOfSection" olarak ayarlarsak,
// her dipnot, metni son notun referans işaretini içeren bölümün sonunda bir koleksiyonda görünecektir.
doc.EndnoteOptions.Position = endnotePosition;

doc.Save(ArtifactsDir + "InlineStory.PositionEndnote.docx");
```

### Ayrıca bakınız

* enum [EndnotePosition](../../endnoteposition/)
* class [EndnoteOptions](../)
* ad alanı [Aspose.Words.Notes](../../endnoteoptions/)
* toplantı [Aspose.Words](../../../)


