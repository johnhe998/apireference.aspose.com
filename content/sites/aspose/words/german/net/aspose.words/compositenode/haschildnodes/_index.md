---
title: CompositeNode.HasChildNodes
second_title: Aspose.Words für .NET-API-Referenz
description: CompositeNode eigendom. Gibt wahr zurück wenn dieser Knoten untergeordnete Knoten hat.
type: docs
weight: 40
url: /de/net/aspose.words/compositenode/haschildnodes/
---
## CompositeNode.HasChildNodes property

Gibt wahr zurück, wenn dieser Knoten untergeordnete Knoten hat.

```csharp
public bool HasChildNodes { get; }
```

### Beispiele

Zeigt, wie die Zeilen aus zwei Tabellen zu einer kombiniert werden.

```csharp
Document doc = new Document(MyDir + "Tables.docx");

// Im Folgenden finden Sie zwei Möglichkeiten, eine Tabelle aus einem Dokument zu erhalten.
// 1 - Aus der "Tables"-Sammlung eines Body-Knotens:
Table firstTable = doc.FirstSection.Body.Tables[0];

// 2 - Verwendung der "GetChild"-Methode:
Table secondTable = (Table)doc.GetChild(NodeType.Table, 1, true);

// Alle Zeilen der aktuellen Tabelle an die nächste anhängen.
while (secondTable.HasChildNodes)
    firstTable.Rows.Add(secondTable.FirstRow);

// Entferne den leeren Tabellencontainer.
secondTable.Remove();

doc.Save(ArtifactsDir + "Table.CombineTables.docx");
```

### Siehe auch

* class [CompositeNode](../)
* namensraum [Aspose.Words](../../compositenode/)
* Montage [Aspose.Words](../../../)


