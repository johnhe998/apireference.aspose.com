---
title: XmlMapping.StoreItemId
second_title: Aspose.Words für .NET-API-Referenz
description: XmlMapping eigendom. Gibt den benutzerdefinierten XMLDatenbezeichner für den benutzerdefinierten XMLDatenteil an der zur Auswertung verwendet werden sollXPath Ausdruck.
type: docs
weight: 40
url: /de/net/aspose.words.markup/xmlmapping/storeitemid/
---
## XmlMapping.StoreItemId property

Gibt den benutzerdefinierten XML-Datenbezeichner für den benutzerdefinierten XML-Datenteil an, der zur Auswertung verwendet werden soll[`XPath`](../xpath/) Ausdruck.

```csharp
public string StoreItemId { get; }
```

### Beispiele

Zeigt, wie der benutzerdefinierte XML-Datenbezeichner eines XML-Teils abgerufen wird.

```csharp
Document doc = new Document(MyDir + "Custom XML part in structured document tag.docx");

// Strukturierte Dokument-Tags haben IDs in Form von GUIDs.
StructuredDocumentTag tag = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);

Assert.AreEqual("{F3029283-4FF8-4DD2-9F31-395F19ACEE85}", tag.XmlMapping.StoreItemId);
```

### Siehe auch

* class [XmlMapping](../)
* namensraum [Aspose.Words.Markup](../../xmlmapping/)
* Montage [Aspose.Words](../../../)


