---
title: Document.OriginalLoadFormat
second_title: Aspose.Words för .NET API Referens
description: Document fast egendom. Hämtar formatet för originaldokumentet som laddades in i detta objekt.
type: docs
weight: 280
url: /sv/net/aspose.words/document/originalloadformat/
---
## Document.OriginalLoadFormat property

Hämtar formatet för originaldokumentet som laddades in i detta objekt.

```csharp
public LoadFormat OriginalLoadFormat { get; }
```

### Anmärkningar

Om du skapade ett nytt tomt dokument returnerasDoc värde.

### Exempel

Visar hur man hämtar information om ett dokuments laddningsoperation.

```csharp
Document doc = new Document(MyDir + "Document.docx");

Assert.AreEqual(MyDir + "Document.docx", doc.OriginalFileName);
Assert.AreEqual(LoadFormat.Docx, doc.OriginalLoadFormat);
```

### Se även

* enum [LoadFormat](../../loadformat/)
* class [Document](../)
* namnutrymme [Aspose.Words](../../document/)
* hopsättning [Aspose.Words](../../../)


