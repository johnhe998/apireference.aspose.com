---
title: CompositeNode.RemoveChild
linktitle: RemoveChild
articleTitle: RemoveChild
second_title: Aspose.Words for .NET
description: CompositeNode RemoveChild method. Removes the specified child node in C#.
type: docs
weight: 170
url: /net/aspose.words/compositenode/removechild/
---
## CompositeNode.RemoveChild method

Removes the specified child node.

```csharp
public Node RemoveChild(Node oldChild)
```

| Parameter | Type | Description |
| --- | --- | --- |
| oldChild | Node | The node to remove. |

### Return Value

The removed node.

## Remarks

The parent of *oldChild* is set to `null` after the node is removed.

## Examples

Shows how to use of methods of Node and CompositeNode to remove a section before the last section in the document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Section 1 text.");
builder.InsertBreak(BreakType.SectionBreakContinuous);
builder.Writeln("Section 2 text.");

// Both sections are siblings of each other.
Section lastSection = (Section)doc.LastChild;
Section firstSection = (Section)lastSection.PreviousSibling;

// Remove a section based on its sibling relationship with another section.
if (lastSection.PreviousSibling != null)
    doc.RemoveChild(firstSection);

// The section we removed was the first one, leaving the document with only the second.
Assert.AreEqual("Section 2 text.", doc.GetText().Trim());
```

### See Also

* class [Node](../../node/)
* class [CompositeNode](../)
* namespace [Aspose.Words](../../../aspose.words/)
* assembly [Aspose.Words](../../../)
