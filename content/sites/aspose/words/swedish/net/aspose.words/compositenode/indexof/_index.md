---
title: CompositeNode.IndexOf
second_title: Aspose.Words för .NET API Referens
description: CompositeNode metod. Returnerar indexet för den angivna undernoden i den underordnade nodmatrisen.
type: docs
weight: 130
url: /sv/net/aspose.words/compositenode/indexof/
---
## CompositeNode.IndexOf method

Returnerar indexet för den angivna undernoden i den underordnade nodmatrisen.

```csharp
public int IndexOf(Node child)
```

### Anmärkningar

Returnerar -1 om noden inte hittas i de underordnade noderna.

### Exempel

Visar hur man hämtar indexet för en given underordnad nod från dess förälder.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

Body body = doc.FirstSection.Body;

// Hämta indexet för det sista stycket i brödtexten i det första avsnittet.
Assert.AreEqual(24, body.ChildNodes.IndexOf(body.LastParagraph));
```

### Se även

* class [Node](../../node/)
* class [CompositeNode](../)
* namnutrymme [Aspose.Words](../../compositenode/)
* hopsättning [Aspose.Words](../../../)


