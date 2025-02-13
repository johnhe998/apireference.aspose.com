---
title: Node.Clone
second_title: Aspose.Words für .NET-API-Referenz
description: Node methode. Erstellt ein Duplikat des Knotens.
type: docs
weight: 100
url: /de/net/aspose.words/node/clone/
---
## Node.Clone method

Erstellt ein Duplikat des Knotens.

```csharp
public Node Clone(bool isCloneChildren)
```

| Parameter | Typ | Beschreibung |
| --- | --- | --- |
| isCloneChildren | Boolean | True, um den Teilbaum unter dem angegebenen Knoten rekursiv zu klonen; false, um nur den Knoten selbst zu klonen. |

### Rückgabewert

Der geklonte Knoten.

### Bemerkungen

Diese Methode dient als Kopierkonstruktor für Knoten. Der geklonte Knoten hat keinen übergeordneten Knoten, gehört aber zu demselben Dokument wie der ursprüngliche Knoten.

Diese Methode führt immer eine tiefe Kopie des Knotens aus. DasistCloneChildren parameter gibt an, ob auch alle untergeordneten Knoten kopiert werden sollen.

### Beispiele

Zeigt, wie ein zusammengesetzter Knoten geklont wird.

```csharp
Document doc = new Document();
Paragraph para = doc.FirstSection.Body.FirstParagraph;
para.AppendChild(new Run(doc, "Hello world!"));

// Im Folgenden finden Sie zwei Möglichkeiten zum Klonen eines zusammengesetzten Knotens.
// 1 - Erstellen Sie einen Klon eines Knotens und erstellen Sie auch einen Klon von jedem seiner untergeordneten Knoten.
Node cloneWithChildren = para.Clone(true);

Assert.IsTrue(((CompositeNode)cloneWithChildren).HasChildNodes);
Assert.AreEqual("Hello world!", cloneWithChildren.GetText().Trim());

// 2 - Erstellen Sie einen Klon eines Knotens ohne Kinder.
Node cloneWithoutChildren = para.Clone(false);

Assert.IsFalse(((CompositeNode)cloneWithoutChildren).HasChildNodes);
Assert.AreEqual(string.Empty, cloneWithoutChildren.GetText().Trim());
```

### Siehe auch

* class [Node](../)
* namensraum [Aspose.Words](../../node/)
* Montage [Aspose.Words](../../../)


