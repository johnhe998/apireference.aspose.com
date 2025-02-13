---
title: Story.StoryType
second_title: Aspose.Words för .NET API Referens
description: Story fast egendom. Hämtar typen av denna berättelse.
type: docs
weight: 40
url: /sv/net/aspose.words/story/storytype/
---
## Story.StoryType property

Hämtar typen av denna berättelse.

```csharp
public StoryType StoryType { get; }
```

### Exempel

Visar hur man tar bort alla former från en nod.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Använd en DocumentBuilder för att infoga en form. Detta är en inline-form,
// som har ett överordnat stycke, som är en underordnad nod till det första avsnittets Kropp.
builder.InsertShape(ShapeType.Cube, 100.0, 100.0);

Assert.AreEqual(1, doc.GetChildNodes(NodeType.Shape, true).Count);

// Vi kan ta bort alla former från underordnade stycken i denna Body.
Assert.AreEqual(StoryType.MainText, doc.FirstSection.Body.StoryType);
doc.FirstSection.Body.DeleteShapes();

Assert.AreEqual(0, doc.GetChildNodes(NodeType.Shape, true).Count);
```

### Se även

* enum [StoryType](../../storytype/)
* class [Story](../)
* namnutrymme [Aspose.Words](../../story/)
* hopsättning [Aspose.Words](../../../)


