---
title: PlainTextDocument.BuiltInDocumentProperties
second_title: Aspose.Words for .NET API Referansı
description: PlainTextDocument mülk. AlırBuiltInDocumentProperties belgenin.
type: docs
weight: 20
url: /tr/net/aspose.words/plaintextdocument/builtindocumentproperties/
---
## PlainTextDocument.BuiltInDocumentProperties property

Alır`BuiltInDocumentProperties` belgenin.

```csharp
public BuiltInDocumentProperties BuiltInDocumentProperties { get; }
```

### Örnekler

Bir Microsoft Word belgesinin içeriğinin düz metin olarak nasıl yükleneceğini ve ardından orijinal belgenin yerleşik özelliklerine nasıl erişileceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Hello world!");
doc.BuiltInDocumentProperties.Author = "John Doe";

doc.Save(ArtifactsDir + "PlainTextDocument.BuiltInProperties.docx");

PlainTextDocument plaintext = new PlainTextDocument(ArtifactsDir + "PlainTextDocument.BuiltInProperties.docx");

Assert.AreEqual("Hello world!", plaintext.Text.Trim());
Assert.AreEqual("John Doe", plaintext.BuiltInDocumentProperties.Author);
```

### Ayrıca bakınız

* class [BuiltInDocumentProperties](../../../aspose.words.properties/builtindocumentproperties/)
* class [PlainTextDocument](../)
* ad alanı [Aspose.Words](../../plaintextdocument/)
* toplantı [Aspose.Words](../../../)


