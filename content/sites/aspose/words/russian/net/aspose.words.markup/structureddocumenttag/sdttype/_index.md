---
title: StructuredDocumentTag.SdtType
second_title: Справочник по API Aspose.Words для .NET
description: StructuredDocumentTag свойство. Получает тип этого Тег структурированного документа .
type: docs
weight: 250
url: /ru/net/aspose.words.markup/structureddocumenttag/sdttype/
---
## StructuredDocumentTag.SdtType property

Получает тип этого **Тег структурированного документа** .

```csharp
public SdtType SdtType { get; }
```

### Примеры

Показывает, как получить тип тега структурированного документа.

```csharp
Document doc = new Document(MyDir + "Structured document tags.docx");

List<StructuredDocumentTag> tags = doc.GetChildNodes(NodeType.StructuredDocumentTag, true)
    .OfType<StructuredDocumentTag>().ToList();

Assert.AreEqual(SdtType.RepeatingSection, tags[0].SdtType);
Assert.AreEqual(SdtType.RepeatingSectionItem, tags[1].SdtType);
Assert.AreEqual(SdtType.RichText, tags[2].SdtType);
```

### Смотрите также

* enum [SdtType](../../sdttype/)
* class [StructuredDocumentTag](../)
* пространство имен [Aspose.Words.Markup](../../structureddocumenttag/)
* сборка [Aspose.Words](../../../)


