---
title: FindReplaceOptions.ApplyParagraphFormat
second_title: Aspose.Words for .NET API Referansı
description: FindReplaceOptions mülk. Paragraf biçimlendirmesi yeni içeriğe uygulandı.
type: docs
weight: 30
url: /tr/net/aspose.words.replacing/findreplaceoptions/applyparagraphformat/
---
## FindReplaceOptions.ApplyParagraphFormat property

Paragraf biçimlendirmesi yeni içeriğe uygulandı.

```csharp
public ParagraphFormat ApplyParagraphFormat { get; }
```

### Örnekler

Bul ve değiştir işleminin eşleşme bulduğu paragraflara biçimlendirmenin nasıl ekleneceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Every paragraph that ends with a full stop like this one will be right aligned.");
builder.Writeln("This one will not!");
builder.Write("This one also will.");

ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;

Assert.AreEqual(ParagraphAlignment.Left, paragraphs[0].ParagraphFormat.Alignment);
Assert.AreEqual(ParagraphAlignment.Left, paragraphs[1].ParagraphFormat.Alignment);
Assert.AreEqual(ParagraphAlignment.Left, paragraphs[2].ParagraphFormat.Alignment);

// Bul ve değiştir işlemini değiştirmek için bir "FindReplaceOptions" nesnesi kullanabiliriz.
FindReplaceOptions options = new FindReplaceOptions();

// Her paragrafı sağa hizalamak için "Alignment" özelliğini "ParagraphAlignment.Right" olarak ayarlayın
// bul ve değiştir işleminin bulduğu bir eşleşmeyi içeren.
options.ApplyParagraphFormat.Alignment = ParagraphAlignment.Right;

// Paragraf sonundan hemen önceki her noktayı bir ünlem işaretiyle değiştirin.
int count = doc.Range.Replace(".&p", "!&p", options);

Assert.AreEqual(2, count);
Assert.AreEqual(ParagraphAlignment.Right, paragraphs[0].ParagraphFormat.Alignment);
Assert.AreEqual(ParagraphAlignment.Left, paragraphs[1].ParagraphFormat.Alignment);
Assert.AreEqual(ParagraphAlignment.Right, paragraphs[2].ParagraphFormat.Alignment);
Assert.AreEqual("Every paragraph that ends with a full stop like this one will be right aligned!\r" +
                "This one will not!\r" +
                "This one also will!", doc.GetText().Trim());
```

### Ayrıca bakınız

* class [ParagraphFormat](../../../aspose.words/paragraphformat/)
* class [FindReplaceOptions](../)
* ad alanı [Aspose.Words.Replacing](../../findreplaceoptions/)
* toplantı [Aspose.Words](../../../)


