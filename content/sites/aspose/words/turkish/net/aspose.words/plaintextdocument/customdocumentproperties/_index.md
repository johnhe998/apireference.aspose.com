---
title: PlainTextDocument.CustomDocumentProperties
second_title: Aspose.Words for .NET API Referansı
description: PlainTextDocument mülk. AlırCustomDocumentProperties belgenin.
type: docs
weight: 30
url: /tr/net/aspose.words/plaintextdocument/customdocumentproperties/
---
## PlainTextDocument.CustomDocumentProperties property

Alır`CustomDocumentProperties` belgenin.

```csharp
public CustomDocumentProperties CustomDocumentProperties { get; }
```

### Örnekler

Bir Microsoft Word belgesinin içeriğinin düz metin olarak nasıl yükleneceğini ve ardından orijinal belgenin özel özelliklerine nasıl erişileceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Hello world!");
doc.CustomDocumentProperties.Add("Location of writing", "123 Main St, London, UK");

doc.Save(ArtifactsDir + "PlainTextDocument.CustomDocumentProperties.docx");

PlainTextDocument plaintext = new PlainTextDocument(ArtifactsDir + "PlainTextDocument.CustomDocumentProperties.docx");

Assert.AreEqual("Hello world!", plaintext.Text.Trim());
Assert.AreEqual("123 Main St, London, UK", plaintext.CustomDocumentProperties["Location of writing"].Value);
```

### Ayrıca bakınız

* class [CustomDocumentProperties](../../../aspose.words.properties/customdocumentproperties/)
* class [PlainTextDocument](../)
* ad alanı [Aspose.Words](../../plaintextdocument/)
* toplantı [Aspose.Words](../../../)


