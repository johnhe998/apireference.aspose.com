---
title: SubDocument.NodeType
second_title: Aspose.Words for .NET API Referansı
description: SubDocument mülk. İade DüğümTürü.Alt Belge
type: docs
weight: 10
url: /tr/net/aspose.words/subdocument/nodetype/
---
## SubDocument.NodeType property

İade **DüğümTürü.Alt Belge**

```csharp
public override NodeType NodeType { get; }
```

### Örnekler

Bir ana belgenin alt belgesine nasıl erişileceğini gösterir.

```csharp
Document doc = new Document(MyDir + "Master document.docx");

NodeCollection subDocuments = doc.GetChildNodes(NodeType.SubDocument, true);
// Bu düğüm, harici bir belgeye referans görevi görür ve içeriğine erişilemez.
SubDocument subDocument = (SubDocument)subDocuments[0];

Assert.False(subDocument.IsComposite);
```

### Ayrıca bakınız

* enum [NodeType](../../nodetype/)
* class [SubDocument](../)
* ad alanı [Aspose.Words](../../subdocument/)
* toplantı [Aspose.Words](../../../)


