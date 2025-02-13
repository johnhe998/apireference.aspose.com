---
title: EndnoteOptions.NumberStyle
second_title: Aspose.Words for .NET API Referansı
description: EndnoteOptions mülk. Otomatik olarak numaralandırılmış son notlar için sayı biçimini belirtir.
type: docs
weight: 10
url: /tr/net/aspose.words.notes/endnoteoptions/numberstyle/
---
## EndnoteOptions.NumberStyle property

Otomatik olarak numaralandırılmış son notlar için sayı biçimini belirtir.

```csharp
public NumberStyle NumberStyle { get; set; }
```

### Notlar

Bu özellik için tüm sayı stilleri geçerli değildir. Uygulanabilir sayı stillerinin listesi için Microsoft Word'deki Dipnot veya Sonnot Ekle iletişim kutusuna bakın. Geçerli olmayan bir sayı stili seçerseniz, Microsoft Word varsayılan bir değere döner.

### Örnekler

Dipnot/sonnot referans işaretlerinin sayı stilinin nasıl değiştirileceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Dipnotlar ve son notlar, metne referans veya yan yorum eklemenin bir yoludur
// ana gövde metninin akışını engellemez. 
// Bir dipnot/sonnot eklemek, küçük bir üst simge referans sembolü ekler
// dipnotu/son notu eklediğimiz ana gövde metninde.
// Her dipnot/sonnot aynı zamanda referansla eşleşen bir sembolden oluşan bir giriş oluşturur.
// ana gövde metninde sembol. Belge oluşturucunun "InsertEndnote" yöntemine ilettiğimiz referans metni.
// Dipnot girişleri, varsayılan olarak, aşağıdakileri içeren her sayfanın altında görünür:
// referans sembolleri ve son notları belgenin sonunda görünür.
builder.Write("Text 1. ");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote 1.");
builder.Write("Text 2. ");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote 2.");
builder.Write("Text 3. ");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote 3.", "Custom footnote reference mark");

builder.InsertParagraph();

builder.Write("Text 1. ");
builder.InsertFootnote(FootnoteType.Endnote, "Endnote 1.");
builder.Write("Text 2. ");
builder.InsertFootnote(FootnoteType.Endnote, "Endnote 2.");
builder.Write("Text 3. ");
builder.InsertFootnote(FootnoteType.Endnote, "Endnote 3.", "Custom endnote reference mark");

// Varsayılan olarak, her dipnot ve son not için referans sembolü, onun indeksidir.
// tüm belgenin dipnotları/son notları arasında. Her belge ayrı sayıları tutar
// dipnotlar ve son notlar için. Varsayılan olarak, dipnotlar numaralarını Arap rakamları kullanarak gösterir,
// ve son notlar numaralarını küçük Romen rakamlarıyla görüntüler.
Assert.AreEqual(NumberStyle.Arabic, doc.FootnoteOptions.NumberStyle);
Assert.AreEqual(NumberStyle.LowercaseRoman, doc.EndnoteOptions.NumberStyle);

// Dipnotlara ve son notlara özel numaralandırma stilleri uygulamak için "NumberStyle" özelliğini kullanabiliriz.
// Bu, özel referans işaretli dipnotları/son notları etkilemez.
doc.FootnoteOptions.NumberStyle = NumberStyle.UppercaseRoman;
doc.EndnoteOptions.NumberStyle = NumberStyle.UppercaseLetter;

doc.Save(ArtifactsDir + "InlineStory.RefMarkNumberStyle.docx");
```

### Ayrıca bakınız

* enum [NumberStyle](../../../aspose.words/numberstyle/)
* class [EndnoteOptions](../)
* ad alanı [Aspose.Words.Notes](../../endnoteoptions/)
* toplantı [Aspose.Words](../../../)


