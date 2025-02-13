---
title: NodeCollection.Insert
second_title: Aspose.Words för .NET API Referens
description: NodeCollection metod. Infogar en nod i samlingen vid det angivna indexet.
type: docs
weight: 80
url: /sv/net/aspose.words/nodecollection/insert/
---
## NodeCollection.Insert method

Infogar en nod i samlingen vid det angivna indexet.

```csharp
public void Insert(int index, Node node)
```

| Parameter | Typ | Beskrivning |
| --- | --- | --- |
| index | Int32 | Det nollbaserade indexet för noden. Negativa index är tillåtna och indikerar åtkomst från baksidan av listan. Till exempel betyder -1 den sista noden, -2 betyder näst före sist och så vidare. |
| node | Node | Noden som ska infogas. |

### Undantag

| undantag | skick |
| --- | --- |
| NotSupportedException | De **NodeCollection** är en "djup" samling. |

### Anmärkningar

Noden infogas som ett underordnat objekt i nodobjektet från vilket samlingen skapades.

Om indexet är lika med eller större än Count läggs noden till i slutet av samlingen.

Om indexet är negativt och dess absoluta värde är större än Count, läggs noden till i slutet av samlingen.

Om det nya barnet redan finns i trädet tas det först bort.

Om noden som infogas skapades från ett annat dokument bör du använda [`ImportNode`](../../documentbase/importnode/) för att importera noden till det aktuella dokumentet. Den importerade noden kan sedan infogas i det aktuella dokumentet.

### Exempel

Visar hur man arbetar med en NodeCollection.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Lägg till text i dokumentet genom att infoga Runs med hjälp av en DocumentBuilder.
builder.Write("Run 1. ");
builder.Write("Run 2. ");

// Varje anrop av "Write"-metoden skapar en ny körning,
// som sedan visas i den överordnade Paragraphs RunCollection.
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;

Assert.AreEqual(2, runs.Count);

// Vi kan också infoga en nod i RunCollection manuellt.
Run newRun = new Run(doc, "Run 3. ");
runs.Insert(3, newRun);

Assert.True(runs.Contains(newRun));
Assert.AreEqual("Run 1. Run 2. Run 3.", doc.GetText().Trim());

// Gå till enskilda körningar och ta bort dem för att ta bort deras text från dokumentet.
Run run = runs[1];
runs.Remove(run);

Assert.AreEqual("Run 1. Run 3.", doc.GetText().Trim());
Assert.NotNull(run);
Assert.False(runs.Contains(run));
```

### Se även

* class [Node](../../node/)
* class [NodeCollection](../)
* namnutrymme [Aspose.Words](../../nodecollection/)
* hopsättning [Aspose.Words](../../../)


