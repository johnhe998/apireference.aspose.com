---
title: SubDocument.NodeType
second_title: Aspose.Words för .NET API Referens
description: SubDocument fast egendom. Returnerar NodeType.SubDocument
type: docs
weight: 10
url: /sv/net/aspose.words/subdocument/nodetype/
---
## SubDocument.NodeType property

Returnerar **NodeType.SubDocument**

```csharp
public override NodeType NodeType { get; }
```

### Exempel

Visar hur man kommer åt ett huvuddokuments underdokument.

```csharp
Document doc = new Document(MyDir + "Master document.docx");

NodeCollection subDocuments = doc.GetChildNodes(NodeType.SubDocument, true);
// Denna nod fungerar som en referens till ett externt dokument, och dess innehåll kan inte nås.
SubDocument subDocument = (SubDocument)subDocuments[0];

Assert.False(subDocument.IsComposite);
```

### Se även

* enum [NodeType](../../nodetype/)
* class [SubDocument](../)
* namnutrymme [Aspose.Words](../../subdocument/)
* hopsättning [Aspose.Words](../../../)


