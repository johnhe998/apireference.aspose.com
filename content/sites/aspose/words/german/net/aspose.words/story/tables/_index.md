---
title: Story.Tables
second_title: Aspose.Words für .NET-API-Referenz
description: Story eigendom. Ruft eine Sammlung von Tabellen ab die unmittelbar untergeordnete Elemente der Story sind.
type: docs
weight: 50
url: /de/net/aspose.words/story/tables/
---
## Story.Tables property

Ruft eine Sammlung von Tabellen ab, die unmittelbar untergeordnete Elemente der Story sind.

```csharp
public TableCollection Tables { get; }
```

### Beispiele

Zeigt, wie die erste und letzte Zeile aller Tabellen in einem Dokument entfernt werden.

```csharp
Document doc = new Document(MyDir + "Tables.docx");

TableCollection tables = doc.FirstSection.Body.Tables;

Assert.AreEqual(5, tables[0].Rows.Count);
Assert.AreEqual(4, tables[1].Rows.Count);

foreach (Table table in tables.OfType<Table>())
{
    table.FirstRow?.Remove();
    table.LastRow?.Remove();
}

Assert.AreEqual(3, tables[0].Rows.Count);
Assert.AreEqual(2, tables[1].Rows.Count);
```

### Siehe auch

* class [TableCollection](../../../aspose.words.tables/tablecollection/)
* class [Story](../)
* namensraum [Aspose.Words](../../story/)
* Montage [Aspose.Words](../../../)


