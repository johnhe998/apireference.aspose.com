---
title: StructuredDocumentTag.SdtType
second_title: Aspose.Words för .NET API Referens
description: StructuredDocumentTag fast egendom. Får typ av detta Strukturerad dokumenttagg .
type: docs
weight: 250
url: /sv/net/aspose.words.markup/structureddocumenttag/sdttype/
---
## StructuredDocumentTag.SdtType property

Får typ av detta **Strukturerad dokumenttagg** .

```csharp
public SdtType SdtType { get; }
```

### Exempel

Visar hur du får typen av en strukturerad dokumenttagg.

```csharp
Document doc = new Document(MyDir + "Structured document tags.docx");

List<StructuredDocumentTag> tags = doc.GetChildNodes(NodeType.StructuredDocumentTag, true)
    .OfType<StructuredDocumentTag>().ToList();

Assert.AreEqual(SdtType.RepeatingSection, tags[0].SdtType);
Assert.AreEqual(SdtType.RepeatingSectionItem, tags[1].SdtType);
Assert.AreEqual(SdtType.RichText, tags[2].SdtType);
```

### Se även

* enum [SdtType](../../sdttype/)
* class [StructuredDocumentTag](../)
* namnutrymme [Aspose.Words.Markup](../../structureddocumenttag/)
* hopsättning [Aspose.Words](../../../)


