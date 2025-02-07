---
title: DocumentProperty.IsLinkToContent
second_title: Aspose.Words für .NET-API-Referenz
description: DocumentProperty eigendom. Zeigt an ob diese Eigenschaft mit Inhalt verknüpft ist oder nicht.
type: docs
weight: 10
url: /de/net/aspose.words.properties/documentproperty/islinktocontent/
---
## DocumentProperty.IsLinkToContent property

Zeigt an, ob diese Eigenschaft mit Inhalt verknüpft ist oder nicht.

```csharp
public bool IsLinkToContent { get; }
```

### Beispiele

Zeigt, wie eine benutzerdefinierte Dokumenteigenschaft mit einem Lesezeichen verknüpft wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.StartBookmark("MyBookmark");
builder.Write("Hello world!");
builder.EndBookmark("MyBookmark");

// Eine neue benutzerdefinierte Eigenschaft mit einem Lesezeichen verknüpfen. Der Wert dieser Eigenschaft
// ist der Inhalt des Lesezeichens, auf das es im "LinkSource"-Member verweist.
CustomDocumentProperties customProperties = doc.CustomDocumentProperties;
DocumentProperty customProperty = customProperties.AddLinkToContent("Bookmark", "MyBookmark");

Assert.AreEqual(true, customProperty.IsLinkToContent);
Assert.AreEqual("MyBookmark", customProperty.LinkSource);
Assert.AreEqual("Hello world!", customProperty.Value);

doc.Save(ArtifactsDir + "DocumentProperties.LinkCustomDocumentPropertiesToBookmark.docx");
```

### Siehe auch

* class [DocumentProperty](../)
* namensraum [Aspose.Words.Properties](../../documentproperty/)
* Montage [Aspose.Words](../../../)


