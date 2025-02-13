---
title: Node.Clone
second_title: Aspose.Words för .NET API Referens
description: Node metod. Skapar en dubblett av noden.
type: docs
weight: 100
url: /sv/net/aspose.words/node/clone/
---
## Node.Clone method

Skapar en dubblett av noden.

```csharp
public Node Clone(bool isCloneChildren)
```

| Parameter | Typ | Beskrivning |
| --- | --- | --- |
| isCloneChildren | Boolean | True för att rekursivt klona underträdet under den angivna noden; false för att endast klona själva noden. |

### Returvärde

Den klonade noden.

### Anmärkningar

Denna metod fungerar som en kopieringskonstruktor för noder. Den klonade noden har ingen förälder, men tillhör samma dokument som den ursprungliga noden.

Denna metod utför alltid en djup kopia av noden. Deär CloneChildren parameter anger om alla underordnade noder ska kopieras också.

### Exempel

Visar hur man klona en sammansatt nod.

```csharp
Document doc = new Document();
Paragraph para = doc.FirstSection.Body.FirstParagraph;
para.AppendChild(new Run(doc, "Hello world!"));

// Nedan finns två sätt att klona en sammansatt nod.
// 1 - Skapa en klon av en nod, och skapa en klon av var och en av dess undernoder.
Node cloneWithChildren = para.Clone(true);

Assert.IsTrue(((CompositeNode)cloneWithChildren).HasChildNodes);
Assert.AreEqual("Hello world!", cloneWithChildren.GetText().Trim());

// 2 - Skapa en klon av en nod helt av sig själv utan några barn.
Node cloneWithoutChildren = para.Clone(false);

Assert.IsFalse(((CompositeNode)cloneWithoutChildren).HasChildNodes);
Assert.AreEqual(string.Empty, cloneWithoutChildren.GetText().Trim());
```

### Se även

* class [Node](../)
* namnutrymme [Aspose.Words](../../node/)
* hopsättning [Aspose.Words](../../../)


