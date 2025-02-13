---
title: CellFormat.Borders
second_title: Aspose.Words per .NET API Reference
description: CellFormat proprietà. Ottiene la raccolta dei bordi della cella.
type: docs
weight: 10
url: /it/net/aspose.words.tables/cellformat/borders/
---
## CellFormat.Borders property

Ottiene la raccolta dei bordi della cella.

```csharp
public BorderCollection Borders { get; }
```

### Esempi

Mostra come combinare le righe di due tabelle in una.

```csharp
Document doc = new Document(MyDir + "Tables.docx");

// Di seguito sono riportati due modi per ottenere una tabella da un documento.
// 1 - Dalla raccolta "Tables" di un nodo Body:
Table firstTable = doc.FirstSection.Body.Tables[0];

// 2 - Utilizzando il metodo "GetChild":
Table secondTable = (Table)doc.GetChild(NodeType.Table, 1, true);

// Aggiunge tutte le righe dalla tabella corrente alla successiva.
while (secondTable.HasChildNodes)
    firstTable.Rows.Add(secondTable.FirstRow);

// Rimuove il contenitore della tabella vuoto.
secondTable.Remove();

doc.Save(ArtifactsDir + "Table.CombineTables.docx");
```

### Guarda anche

* class [BorderCollection](../../../aspose.words/bordercollection/)
* class [CellFormat](../)
* spazio dei nomi [Aspose.Words.Tables](../../cellformat/)
* assemblea [Aspose.Words](../../../)


