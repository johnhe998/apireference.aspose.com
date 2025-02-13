---
title: SubDocument.NodeType
second_title: Справочник по API Aspose.Words для .NET
description: SubDocument свойство. Возвращает NodeType.SubDocument
type: docs
weight: 10
url: /ru/net/aspose.words/subdocument/nodetype/
---
## SubDocument.NodeType property

Возвращает **NodeType.SubDocument**

```csharp
public override NodeType NodeType { get; }
```

### Примеры

Показывает, как получить доступ к поддокументу главного документа.

```csharp
Document doc = new Document(MyDir + "Master document.docx");

NodeCollection subDocuments = doc.GetChildNodes(NodeType.SubDocument, true);
// Этот узел служит ссылкой на внешний документ, и его содержимое недоступно.
SubDocument subDocument = (SubDocument)subDocuments[0];

Assert.False(subDocument.IsComposite);
```

### Смотрите также

* enum [NodeType](../../nodetype/)
* class [SubDocument](../)
* пространство имен [Aspose.Words](../../subdocument/)
* сборка [Aspose.Words](../../../)


