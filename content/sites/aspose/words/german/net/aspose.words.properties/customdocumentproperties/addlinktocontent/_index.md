---
title: CustomDocumentProperties.AddLinkToContent
second_title: Aspose.Words für .NET-API-Referenz
description: CustomDocumentProperties methode. Erstellt eine neue mit Inhalt verknüpfte benutzerdefinierte Dokumenteigenschaft.
type: docs
weight: 20
url: /de/net/aspose.words.properties/customdocumentproperties/addlinktocontent/
---
## CustomDocumentProperties.AddLinkToContent method

Erstellt eine neue, mit Inhalt verknüpfte benutzerdefinierte Dokumenteigenschaft.

```csharp
public DocumentProperty AddLinkToContent(string name, string linkSource)
```

| Parameter | Typ | Beschreibung |
| --- | --- | --- |
| name | String | Der Name der Eigenschaft. |
| linkSource | String | Die Quelle der Eigenschaft. |

### Rückgabewert

Das neu erstellte Eigenschaftsobjekt oder null, wenn linkSource ungültig ist.

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

* class [DocumentProperty](../../documentproperty/)
* class [CustomDocumentProperties](../)
* namensraum [Aspose.Words.Properties](../../customdocumentproperties/)
* Montage [Aspose.Words](../../../)


