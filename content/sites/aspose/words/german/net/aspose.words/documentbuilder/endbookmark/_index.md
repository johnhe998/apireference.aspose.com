---
title: DocumentBuilder.EndBookmark
second_title: Aspose.Words für .NET-API-Referenz
description: DocumentBuilder methode. Markiert die aktuelle Position im Dokument als Lesezeichenende.
type: docs
weight: 190
url: /de/net/aspose.words/documentbuilder/endbookmark/
---
## DocumentBuilder.EndBookmark method

Markiert die aktuelle Position im Dokument als Lesezeichenende.

```csharp
public BookmarkEnd EndBookmark(string bookmarkName)
```

| Parameter | Typ | Beschreibung |
| --- | --- | --- |
| bookmarkName | String | Name des Lesezeichens. |

### Rückgabewert

Der Lesezeichen-Endknoten, der gerade erstellt wurde.

### Bemerkungen

Lesezeichen in einem Dokument können sich überschneiden und einen beliebigen Bereich umfassen. Um ein gültiges Lesezeichen zu erstellen, müssen Sie beide aufrufen[`StartBookmark`](../startbookmark/) und`EndBookmark` mit dem gleichen **LesezeichenName** Parameter.

Schlecht formatierte Lesezeichen oder Lesezeichen mit doppelten Namen werden beim Speichern des Dokuments ignoriert.

### Beispiele

Zeigt, wie ein Lesezeichen erstellt wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Ein gültiges Lesezeichen muss einen Dokumentkörpertext enthalten, der von eingeschlossen ist
// BookmarkStart- und BookmarkEnd-Knoten mit passendem Lesezeichennamen erstellt.
builder.StartBookmark("MyBookmark");
builder.Writeln("Hello world!");
builder.EndBookmark("MyBookmark");

Assert.AreEqual(1, doc.Range.Bookmarks.Count);
Assert.AreEqual("MyBookmark", doc.Range.Bookmarks[0].Name);
Assert.AreEqual("Hello world!", doc.Range.Bookmarks[0].Text.Trim());
```

Zeigt, wie ein Hyperlink eingefügt wird, der auf ein lokales Lesezeichen verweist.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.StartBookmark("Bookmark1");
builder.Write("Bookmarked text. ");
builder.EndBookmark("Bookmark1");
builder.Writeln("Text outside of the bookmark.");

// Fügen Sie ein HYPERLINK-Feld ein, das auf das Lesezeichen verweist. Wir können Feldschalter passieren
// an die Methode "InsertHyperlink" als Teil des Arguments, das den Namen des referenzierten Lesezeichens enthält.
builder.Font.Color = Color.Blue;
builder.Font.Underline = Underline.Single;
builder.InsertHyperlink("Link to Bookmark1", @"Bookmark1"" \o ""Hyperlink Tip", true);

doc.Save(ArtifactsDir + "DocumentBuilder.InsertHyperlinkToLocalBookmark.docx");
```

### Siehe auch

* class [BookmarkEnd](../../bookmarkend/)
* class [DocumentBuilder](../)
* namensraum [Aspose.Words](../../documentbuilder/)
* Montage [Aspose.Words](../../../)


