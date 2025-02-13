---
title: Document.Compliance
second_title: Aspose.Words für .NET-API-Referenz
description: Document eigendom. Ruft die aus dem geladenen Dokumentinhalt ermittelte OOXMLKonformitätsversion ab. Nur für OOXMLDokumente sinnvoll.
type: docs
weight: 60
url: /de/net/aspose.words/document/compliance/
---
## Document.Compliance property

Ruft die aus dem geladenen Dokumentinhalt ermittelte OOXML-Konformitätsversion ab. Nur für OOXML-Dokumente sinnvoll.

```csharp
public OoxmlCompliance Compliance { get; }
```

### Bemerkungen

Wenn Sie ein neues leeres Dokument erstellt oder kein OOXML geladen haben, gibt document dieEcma376_2006 Wert.

### Beispiele

Zeigt, wie die Open Office XML-Konformitätsversion eines geladenen Dokuments gelesen wird.

```csharp
// Die Konformitätsversion variiert zwischen Dokumenten, die mit verschiedenen Versionen von Microsoft Word erstellt wurden.
Document doc = new Document(MyDir + "Document.doc");

Assert.AreEqual(doc.Compliance, OoxmlCompliance.Ecma376_2006);

doc = new Document(MyDir + "Document.docx");

Assert.AreEqual(doc.Compliance, OoxmlCompliance.Iso29500_2008_Transitional);
```

### Siehe auch

* enum [OoxmlCompliance](../../../aspose.words.saving/ooxmlcompliance/)
* class [Document](../)
* namensraum [Aspose.Words](../../document/)
* Montage [Aspose.Words](../../../)


