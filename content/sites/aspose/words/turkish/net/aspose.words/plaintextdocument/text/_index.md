---
title: PlainTextDocument.Text
second_title: Aspose.Words for .NET API Referansı
description: PlainTextDocument mülk. Dize olarak birleştirilmiş belgenin metin içeriğini alır.
type: docs
weight: 40
url: /tr/net/aspose.words/plaintextdocument/text/
---
## PlainTextDocument.Text property

Dize olarak birleştirilmiş belgenin metin içeriğini alır.

```csharp
public string Text { get; }
```

### Örnekler

Bir Microsoft Word belgesinin içeriğinin düz metin olarak nasıl yükleneceğini gösterir.

```csharp
Document doc = new Document(); 
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

doc.Save(ArtifactsDir + "PlainTextDocument.Load.docx");

PlainTextDocument plaintext = new PlainTextDocument(ArtifactsDir + "PlainTextDocument.Load.docx");

Assert.AreEqual("Hello world!", plaintext.Text.Trim());
```

### Ayrıca bakınız

* class [PlainTextDocument](../)
* ad alanı [Aspose.Words](../../plaintextdocument/)
* toplantı [Aspose.Words](../../../)


