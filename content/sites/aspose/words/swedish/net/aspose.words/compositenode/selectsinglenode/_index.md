---
title: CompositeNode.SelectSingleNode
second_title: Aspose.Words för .NET API Referens
description: CompositeNode metod. Väljer den första noden som matchar XPathuttrycket.
type: docs
weight: 210
url: /sv/net/aspose.words/compositenode/selectsinglenode/
---
## CompositeNode.SelectSingleNode method

Väljer den första noden som matchar XPath-uttrycket.

```csharp
public Node SelectSingleNode(string xpath)
```

| Parameter | Typ | Beskrivning |
| --- | --- | --- |
| xpath | String | XPath-uttrycket. |

### Returvärde

Den första noden som matchar XPath-frågan eller null om ingen matchande nod hittas.

### Anmärkningar

Endast uttryck med elementnamn stöds för tillfället. Expressions som använder attributnamn stöds inte.

### Exempel

Visar hur man väljer vissa noder med hjälp av ett XPath-uttryck.

```csharp
Document doc = new Document(MyDir + "Tables.docx");

// Detta uttryck extraherar alla styckenoder,
// som är ättlingar till valfri tabellnod i dokumentet.
NodeList nodeList = doc.SelectNodes("//Tabell//Paragraph");

// Iterera genom listan med en uppräkning och skriv ut innehållet i varje stycke i varje cell i tabellen.
int index = 0;

using (IEnumerator<Node> e = nodeList.GetEnumerator())
    while (e.MoveNext())
        Console.WriteLine($"Table paragraph index {index++}, contents: \"{e.Current.GetText().Trim()}\"");

// Detta uttryck kommer att välja alla stycken som är direkta underordnade av någon Kroppsnod i dokumentet.
nodeList = doc.SelectNodes("//Body/Paragraph");

// Vi kan behandla listan som en array.
Assert.AreEqual(4, nodeList.ToArray().Length);

// Använd SelectSingleNode för att välja det första resultatet av samma uttryck som ovan.
Node node = doc.SelectSingleNode("//Body/Paragraph");

Assert.AreEqual(typeof(Paragraph), node.GetType());
```

### Se även

* class [Node](../../node/)
* class [CompositeNode](../)
* namnutrymme [Aspose.Words](../../compositenode/)
* hopsättning [Aspose.Words](../../../)


