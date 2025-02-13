---
title: DocumentBuilder.EndColumnBookmark
second_title: Aspose.Words für .NET-API-Referenz
description: DocumentBuilder methode. Markiert die aktuelle Position im Dokument als SpaltenLesezeichenEnde. Die Position muss sich in einer Tabellenzelle befinden.
type: docs
weight: 200
url: /de/net/aspose.words/documentbuilder/endcolumnbookmark/
---
## DocumentBuilder.EndColumnBookmark method

Markiert die aktuelle Position im Dokument als Spalten-Lesezeichen-Ende. Die Position muss sich in einer Tabellenzelle befinden.

```csharp
public BookmarkEnd EndColumnBookmark(string bookmarkName)
```

| Parameter | Typ | Beschreibung |
| --- | --- | --- |
| bookmarkName | String | Name des Lesezeichens. |

### Rückgabewert

Der Lesezeichen-Endknoten, der gerade erstellt wurde.

### Bemerkungen

Ein Spaltenlesezeichen deckt eine oder mehrere Spalten in einem Bereich von Zeilen ab. Um ein gültiges Lesezeichen zu erstellen, müssen Sie beide aufrufen[`StartColumnBookmark`](../startcolumnbookmark/) und`EndColumnBookmark` mit demselben  **LesezeichenName** Parameter.

Schlecht formatierte Lesezeichen oder Lesezeichen mit doppelten Namen werden beim Speichern des Dokuments ignoriert.

Die tatsächliche Position des eingefügten[`BookmarkEnd`](../../bookmarkend/) node kann sich von der aktuellen document Builder-Position unterscheiden.

### Beispiele

Zeigt, wie ein Spaltenlesezeichen erstellt wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.StartTable();

builder.InsertCell();
// Die Zellen 1,2,4,5 werden mit einem Lesezeichen versehen.
builder.StartColumnBookmark("MyBookmark_1");
// Schlecht formatierte Lesezeichen oder Lesezeichen mit doppelten Namen werden beim Speichern des Dokuments ignoriert.
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

### Siehe auch

* class [BookmarkEnd](../../bookmarkend/)
* class [DocumentBuilder](../)
* namensraum [Aspose.Words](../../documentbuilder/)
* Montage [Aspose.Words](../../../)


