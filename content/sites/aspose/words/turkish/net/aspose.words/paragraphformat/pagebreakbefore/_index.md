---
title: ParagraphFormat.PageBreakBefore
second_title: Aspose.Words for .NET API Referansı
description: ParagraphFormat mülk. Paragraftan önce bir sayfa sonu zorunluysa doğrudur.
type: docs
weight: 250
url: /tr/net/aspose.words/paragraphformat/pagebreakbefore/
---
## ParagraphFormat.PageBreakBefore property

Paragraftan önce bir sayfa sonu zorunluysa doğrudur.

```csharp
public bool PageBreakBefore { get; set; }
```

### Örnekler

Başında sayfa sonları olan paragrafların nasıl oluşturulacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Her paragrafın başına bir sayfa sonu uygulamak için bu bayrağı "true" olarak ayarlayın
// belge oluşturucunun bu ParagraphFormat yapılandırması altında oluşturacağı.
// İlk paragraf sayfa sonu almayacak.
// Her yeni paragrafı aynı sayfada başlatmak için bu bayrağı "yanlış" olarak bırakın
// önceki gibi, yeterli alan olması şartıyla.
builder.ParagraphFormat.PageBreakBefore = pageBreakBefore;

builder.Writeln("Paragraph 1.");
builder.Writeln("Paragraph 2.");

LayoutCollector layoutCollector = new LayoutCollector(doc);
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;

if (pageBreakBefore)
{
    Assert.AreEqual(1, layoutCollector.GetStartPageIndex(paragraphs[0]));
    Assert.AreEqual(2, layoutCollector.GetStartPageIndex(paragraphs[1]));
}
else
{
    Assert.AreEqual(1, layoutCollector.GetStartPageIndex(paragraphs[0]));
    Assert.AreEqual(1, layoutCollector.GetStartPageIndex(paragraphs[1]));
}

doc.Save(ArtifactsDir + "ParagraphFormat.PageBreakBefore.docx");
```

### Ayrıca bakınız

* class [ParagraphFormat](../)
* ad alanı [Aspose.Words](../../paragraphformat/)
* toplantı [Aspose.Words](../../../)


