---
title: Bookmark.LastColumn
second_title: Aspose.Words per .NET API Reference
description: Bookmark proprietà. Ottiene lindice in base zero dellultima colonna dellintervallo di colonne della tabella associato al segnalibro.
type: docs
weight: 50
url: /it/net/aspose.words/bookmark/lastcolumn/
---
## Bookmark.LastColumn property

Ottiene l'indice in base zero dell'ultima colonna dell'intervallo di colonne della tabella associato al segnalibro.

```csharp
public int LastColumn { get; }
```

### Osservazioni

Restituisce **-1** se questo segnalibro non è un segnalibro della colonna della tabella.

### Esempi

Mostra come ottenere informazioni sui segnalibri delle colonne della tabella.

```csharp
Document doc = new Document(MyDir + "Table column bookmarks.doc");

foreach (Bookmark bookmark in doc.Range.Bookmarks)
{
    // Se un segnalibro racchiude colonne di una tabella, è un segnalibro di una colonna di tabella e il relativo flag IsColumn è impostato su true.
    Console.WriteLine($"Bookmark: {bookmark.Name}{(bookmark.IsColumn ? " (Column)" : "")}");
    if (bookmark.IsColumn)
    {
        if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row &&
            bookmark.FirstColumn < row.Cells.Count)
        {
            // Stampa il contenuto della prima e dell'ultima colonna racchiuse dal segnalibro.
            Console.WriteLine(row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar));
            Console.WriteLine(row.Cells[bookmark.LastColumn].GetText().TrimEnd(ControlChar.CellChar));
        }
    }
}
```

### Guarda anche

* class [Bookmark](../)
* spazio dei nomi [Aspose.Words](../../bookmark/)
* assemblea [Aspose.Words](../../../)


