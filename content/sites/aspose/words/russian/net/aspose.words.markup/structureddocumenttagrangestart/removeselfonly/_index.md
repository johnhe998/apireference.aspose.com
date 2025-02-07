---
title: StructuredDocumentTagRangeStart.RemoveSelfOnly
second_title: Справочник по API Aspose.Words для .NET
description: StructuredDocumentTagRangeStart метод. Удаляет это начало диапазона и соответствующие конечные узлы диапазона тега структурированного документа  но сохраняет его содержимое в дереве документа.
type: docs
weight: 240
url: /ru/net/aspose.words.markup/structureddocumenttagrangestart/removeselfonly/
---
## StructuredDocumentTagRangeStart.RemoveSelfOnly method

Удаляет это начало диапазона и соответствующие конечные узлы диапазона тега структурированного документа, , но сохраняет его содержимое в дереве документа.

```csharp
public void RemoveSelfOnly()
```

### Примеры

Показывает, как создать/удалить структурированный тег документа и его содержимое.

```csharp
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.Writeln("StructuredDocumentTag element");

    InsertStructuredDocumentTagRanges(doc, out StructuredDocumentTagRangeStart rangeStart);

    // Удаляет ранжированный структурированный тег документа, но сохраняет содержимое внутри.
    rangeStart.RemoveSelfOnly();

    rangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(
        NodeType.StructuredDocumentTagRangeStart, 0, false);
    Assert.AreEqual(null, rangeStart);

    StructuredDocumentTagRangeEnd rangeEnd = (StructuredDocumentTagRangeEnd)doc.GetChild(
        NodeType.StructuredDocumentTagRangeEnd, 0, false);

    Assert.AreEqual(null, rangeEnd);
    Assert.AreEqual("StructuredDocumentTag element", doc.GetText().Trim());

    InsertStructuredDocumentTagRanges(doc, out rangeStart);

    Node paragraphNode = rangeStart.LastOrDefault();
    Assert.AreEqual("StructuredDocumentTag element", paragraphNode?.GetText().Trim());

    // Удаляет ранжированный структурированный тег документа и содержимое внутри.
    rangeStart.RemoveAllChildren();

    paragraphNode = rangeStart.LastOrDefault();
    Assert.AreEqual(null, paragraphNode?.GetText());
}

public void InsertStructuredDocumentTagRanges(Document doc, out StructuredDocumentTagRangeStart rangeStart)
{
    rangeStart = new StructuredDocumentTagRangeStart(doc, SdtType.PlainText);
    StructuredDocumentTagRangeEnd rangeEnd = new StructuredDocumentTagRangeEnd(doc, rangeStart.Id);

    doc.FirstSection.Body.InsertBefore(rangeStart, doc.FirstSection.Body.FirstParagraph);
    doc.LastSection.Body.InsertAfter(rangeEnd, doc.FirstSection.Body.FirstParagraph);
}
```

### Смотрите также

* class [StructuredDocumentTagRangeStart](../)
* пространство имен [Aspose.Words.Markup](../../structureddocumenttagrangestart/)
* сборка [Aspose.Words](../../../)


