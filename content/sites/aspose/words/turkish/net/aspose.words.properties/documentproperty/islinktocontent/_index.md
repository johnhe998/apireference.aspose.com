---
title: DocumentProperty.IsLinkToContent
second_title: Aspose.Words for .NET API Referansı
description: DocumentProperty mülk. Bu özelliğin içeriğe bağlı olup olmadığını gösterir.
type: docs
weight: 10
url: /tr/net/aspose.words.properties/documentproperty/islinktocontent/
---
## DocumentProperty.IsLinkToContent property

Bu özelliğin içeriğe bağlı olup olmadığını gösterir.

```csharp
public bool IsLinkToContent { get; }
```

### Örnekler

Özel bir belge özelliğinin bir yer işaretine nasıl bağlanacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.StartBookmark("MyBookmark");
builder.Write("Hello world!");
builder.EndBookmark("MyBookmark");

// Yeni bir özel özelliği bir yer işaretine bağla. Bu mülkün değeri
// "LinkSource" üyesinde başvurduğu yer işaretinin içeriği olacaktır.
CustomDocumentProperties customProperties = doc.CustomDocumentProperties;
DocumentProperty customProperty = customProperties.AddLinkToContent("Bookmark", "MyBookmark");

Assert.AreEqual(true, customProperty.IsLinkToContent);
Assert.AreEqual("MyBookmark", customProperty.LinkSource);
Assert.AreEqual("Hello world!", customProperty.Value);

doc.Save(ArtifactsDir + "DocumentProperties.LinkCustomDocumentPropertiesToBookmark.docx");
```

### Ayrıca bakınız

* class [DocumentProperty](../)
* ad alanı [Aspose.Words.Properties](../../documentproperty/)
* toplantı [Aspose.Words](../../../)


