---
title: DocumentBuilder.EndColumnBookmark
second_title: Aspose.Words per .NET API Reference
description: DocumentBuilder metodo. Contrassegna la posizione corrente nel documento come fine di un segnalibro di colonna. La posizione deve essere in una cella di tabella.
type: docs
weight: 200
url: /it/net/aspose.words/documentbuilder/endcolumnbookmark/
---
## DocumentBuilder.EndColumnBookmark method

Contrassegna la posizione corrente nel documento come fine di un segnalibro di colonna. La posizione deve essere in una cella di tabella.

```csharp
public BookmarkEnd EndColumnBookmark(string bookmarkName)
```

| Parametro | Tipo | Descrizione |
| --- | --- | --- |
| bookmarkName | String | Nome del segnalibro. |

### Valore di ritorno

Il nodo finale del segnalibro appena creato.

### Osservazioni

Un segnalibro di colonna copre una o più colonne in un intervallo di righe. Per creare un segnalibro valido devi chiamare entrambi[`StartColumnBookmark`](../startcolumnbookmark/) e`EndColumnBookmark` con lo stesso  **bookmarkName** parametro.

I segnalibri di formato errato o i segnalibri con nomi duplicati verranno ignorati quando il documento viene salvato.

La posizione effettiva dell'inserito[`BookmarkEnd`](../../bookmarkend/) node può differire dalla posizione del builder document corrente.

### Esempi

Mostra come creare un segnalibro di una colonna.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.StartTable();

builder.InsertCell();
// Le celle 1,2,4,5 verranno inserite nei segnalibri.
builder.StartColumnBookmark("MyBookmark_1");
// I segnalibri formati male oi segnalibri con nomi duplicati verranno ignorati quando il documento viene salvato.
builder.StartColumnBookmark("MyBookmark_1");
builder.StartColumnBookmark("BadStartBookmark");
builder.Write("Cell 1");

builder.InsertCell();
builder.Write("Cell 2");

builder.InsertCell();
builder.Write("Cell 3");

builder.EndRow();

builder.InsertCell();
builder.Write("Cell 4");

builder.InsertCell();
builder.Write("Cell 5");
builder.EndColumnBookmark("MyBookmark_1");
builder.EndColumnBookmark("MyBookmark_1");

builder.InsertCell();
builder.Write("Cell 6");

builder.EndRow();
builder.EndTable();

doc.Save(ArtifactsDir + "Bookmarks.CreateColumnBookmark.docx");
```

### Guarda anche

* class [BookmarkEnd](../../bookmarkend/)
* class [DocumentBuilder](../)
* spazio dei nomi [Aspose.Words](../../documentbuilder/)
* assemblea [Aspose.Words](../../../)


