---
title: FootnoteOptions.RestartRule
second_title: Aspose.Words for .NET API Referansı
description: FootnoteOptions mülk. Otomatik numaralandırmanın ne zaman yeniden başlayacağını belirler.
type: docs
weight: 40
url: /tr/net/aspose.words.notes/footnoteoptions/restartrule/
---
## FootnoteOptions.RestartRule property

Otomatik numaralandırmanın ne zaman yeniden başlayacağını belirler.

```csharp
public FootnoteNumberingRule RestartRule { get; set; }
```

### Örnekler

Belgedeki belirli yerlerde dipnot/sonnot numaralandırmanın nasıl yeniden başlatılacağını gösterir.

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
builder.InsertBreak(BreakType.PageBreak);
builder.Write("Text 3. ");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote 3.");
builder.Write("Text 4. ");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote 4.");

builder.InsertBreak(BreakType.PageBreak);

builder.Write("Text 1. ");
builder.InsertFootnote(FootnoteType.Endnote, "Endnote 1.");
builder.Write("Text 2. ");
builder.InsertFootnote(FootnoteType.Endnote, "Endnote 2.");
builder.InsertBreak(BreakType.SectionBreakNewPage);
builder.Write("Text 3. ");
builder.InsertFootnote(FootnoteType.Endnote, "Endnote 3.");
builder.Write("Text 4. ");
builder.InsertFootnote(FootnoteType.Endnote, "Endnote 4.");

// Varsayılan olarak, her dipnot ve son not için referans sembolü, onun indeksidir.
// tüm belgenin dipnotları/son notları arasında. Her belge ayrı sayıları tutar
// dipnotlar ve son notlar için ve bu sayıları hiçbir noktada yeniden başlatmaz.
Assert.AreEqual(doc.FootnoteOptions.RestartRule, FootnoteNumberingRule.Default);
Assert.AreEqual(FootnoteNumberingRule.Default, FootnoteNumberingRule.Continuous);

// Belgeyi yeniden başlatmak için "RestartRule" özelliğini kullanabiliriz
// dipnot/sonnot yeni bir sayfada veya bölümde sayılır.
doc.FootnoteOptions.RestartRule = FootnoteNumberingRule.RestartPage;
doc.EndnoteOptions.RestartRule = FootnoteNumberingRule.RestartSection;

doc.Save(ArtifactsDir + "InlineStory.NumberingRule.docx");
```

### Ayrıca bakınız

* enum [FootnoteNumberingRule](../../footnotenumberingrule/)
* class [FootnoteOptions](../)
* ad alanı [Aspose.Words.Notes](../../footnoteoptions/)
* toplantı [Aspose.Words](../../../)


