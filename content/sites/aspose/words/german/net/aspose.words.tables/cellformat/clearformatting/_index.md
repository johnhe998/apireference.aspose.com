---
title: CellFormat.ClearFormatting
second_title: Aspose.Words für .NET-API-Referenz
description: CellFormat methode. Setzt auf Standardzellenformatierung zurück. Ändert nicht die Breite der Zelle.
type: docs
weight: 150
url: /de/net/aspose.words.tables/cellformat/clearformatting/
---
## CellFormat.ClearFormatting method

Setzt auf Standardzellenformatierung zurück. Ändert nicht die Breite der Zelle.

```csharp
public void ClearFormatting()
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

* class [CellFormat](../)
* namensraum [Aspose.Words.Tables](../../cellformat/)
* Montage [Aspose.Words](../../../)


