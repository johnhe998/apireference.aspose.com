---
title: LayoutOptions.ShowParagraphMarks
second_title: Aspose.Words for .NET API Referansı
description: LayoutOptions mülk. Paragraf işaretlerinin oluşturulup oluşturulmadığının göstergesini alır veya ayarlar. Varsayılan Falsedır.
type: docs
weight: 80
url: /tr/net/aspose.words.layout/layoutoptions/showparagraphmarks/
---
## LayoutOptions.ShowParagraphMarks property

Paragraf işaretlerinin oluşturulup oluşturulmadığının göstergesini alır veya ayarlar. Varsayılan, False'dır.

```csharp
public bool ShowParagraphMarks { get; set; }
```

### Örnekler

İşlenmiş bir çıktı belgesinde paragraf işaretlerinin nasıl gösterileceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
// Bazı paragraflar ekleyin, ardından paragrafların sonlarını göstermek için paragraf işaretlerini etkinleştirin
// belgeyi oluşturduğumuzda bir pilcrow (¶) sembolü ile.
builder.Writeln("Hello world!");
builder.Writeln("Hello again!");

doc.LayoutOptions.ShowParagraphMarks = showParagraphMarks;

doc.Save(ArtifactsDir + "Document.LayoutOptionsParagraphMarks.pdf");
```

### Ayrıca bakınız

* class [LayoutOptions](../)
* ad alanı [Aspose.Words.Layout](../../layoutoptions/)
* toplantı [Aspose.Words](../../../)


