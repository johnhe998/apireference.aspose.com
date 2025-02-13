---
title: NodeCollection.IndexOf
second_title: Aspose.Words für .NET-API-Referenz
description: NodeCollection methode. Gibt den nullbasierten Index des angegebenen Knotens zurück.
type: docs
weight: 70
url: /de/net/aspose.words/nodecollection/indexof/
---
## NodeCollection.IndexOf method

Gibt den nullbasierten Index des angegebenen Knotens zurück.

```csharp
public int IndexOf(Node node)
```

| Parameter | Typ | Beschreibung |
| --- | --- | --- |
| node | Node | Der zu lokalisierende Knoten. |

### Rückgabewert

Der nullbasierte Index des Knotens innerhalb der Sammlung, falls gefunden; andernfalls -1.

### Bemerkungen

Diese Methode führt eine lineare Suche durch; Daher ist die durchschnittliche Ausführungszeit proportional zu Count.

### Beispiele

Zeigt, wie der Index eines Knotens in einer Auflistung abgerufen wird.

```csharp
Document doc = new Document(MyDir + "Tables.docx");

Table table = doc.FirstSection.Body.Tables[0];
NodeCollection allTables = doc.GetChildNodes(NodeType.Table, true);

Assert.AreEqual(0, allTables.IndexOf(table));

Row row = table.Rows[2];

Assert.AreEqual(2, table.IndexOf(row));

Cell cell = row.LastCell;

Assert.AreEqual(4, row.IndexOf(cell));
```

### Siehe auch

* class [Node](../../node/)
* class [NodeCollection](../)
* namensraum [Aspose.Words](../../nodecollection/)
* Montage [Aspose.Words](../../../)


