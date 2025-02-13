---
title: CompositeNode.SelectSingleNode
second_title: Aspose.Words für .NET-API-Referenz
description: CompositeNode methode. Wählt den ersten Knoten aus der mit dem XPathAusdruck übereinstimmt.
type: docs
weight: 210
url: /de/net/aspose.words/compositenode/selectsinglenode/
---
## CompositeNode.SelectSingleNode method

Wählt den ersten Knoten aus, der mit dem XPath-Ausdruck übereinstimmt.

```csharp
public Node SelectSingleNode(string xpath)
```

| Parameter | Typ | Beschreibung |
| --- | --- | --- |
| xpath | String | Der XPath-Ausdruck. |

### Rückgabewert

Der erste Knoten, der mit der XPath-Abfrage übereinstimmt, oder null, wenn kein übereinstimmender Knoten gefunden wird.

### Bemerkungen

Derzeit werden nur Ausdrücke mit Elementnamen unterstützt. Ausdrücke , die Attributnamen verwenden, werden nicht unterstützt.

### Beispiele

Zeigt, wie bestimmte Knoten mithilfe eines XPath-Ausdrucks ausgewählt werden.

```csharp
Document doc = new Document(MyDir + "Tables.docx");

// Dieser Ausdruck extrahiert alle Absatzknoten,
// die Nachkommen eines beliebigen Tabellenknotens im Dokument sind.
NodeList nodeList = doc.SelectNodes("//Tabelle//Absatz");

// Die Liste mit einem Enumerator durchlaufen und den Inhalt jedes Absatzes in jeder Zelle der Tabelle ausgeben.
int index = 0;

using (IEnumerator<Node> e = nodeList.GetEnumerator())
    while (e.MoveNext())
        Console.WriteLine($"Table paragraph index {index++}, contents: \"{e.Current.GetText().Trim()}\"");

// Dieser Ausdruck wählt alle Absätze aus, die direkte Kinder eines beliebigen Body-Knotens im Dokument sind.
nodeList = doc.SelectNodes("//Körperabschnitt");

// Wir können die Liste als Array behandeln.
Assert.AreEqual(4, nodeList.ToArray().Length);

// SelectSingleNode verwenden, um das erste Ergebnis desselben Ausdrucks wie oben auszuwählen.
Node node = doc.SelectSingleNode("//Körperabschnitt");

Assert.AreEqual(typeof(Paragraph), node.GetType());
```

### Siehe auch

* class [Node](../../node/)
* class [CompositeNode](../)
* namensraum [Aspose.Words](../../compositenode/)
* Montage [Aspose.Words](../../../)


