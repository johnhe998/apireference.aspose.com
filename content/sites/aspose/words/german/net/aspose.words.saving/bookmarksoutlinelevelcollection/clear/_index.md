---
title: BookmarksOutlineLevelCollection.Clear
second_title: Aspose.Words für .NET-API-Referenz
description: BookmarksOutlineLevelCollection methode. Entfernt alle Elemente aus der Sammlung.
type: docs
weight: 50
url: /de/net/aspose.words.saving/bookmarksoutlinelevelcollection/clear/
---
## BookmarksOutlineLevelCollection.Clear method

Entfernt alle Elemente aus der Sammlung.

```csharp
public void Clear()
```

### Beispiele

Zeigt, wie Gliederungsebenen für Lesezeichen festgelegt werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Fügen Sie ein Lesezeichen mit einem anderen darin verschachtelten Lesezeichen ein.
builder.StartBookmark("Bookmark 1");
builder.Writeln("Text inside Bookmark 1.");

builder.StartBookmark("Bookmark 2");
builder.Writeln("Text inside Bookmark 1 and 2.");
builder.EndBookmark("Bookmark 2");

builder.Writeln("Text inside Bookmark 1.");
builder.EndBookmark("Bookmark 1");

// Ein weiteres Lesezeichen einfügen.
builder.StartBookmark("Bookmark 3");
builder.Writeln("Text inside Bookmark 3.");
builder.EndBookmark("Bookmark 3");

// Beim Speichern im PDF-Format können Lesezeichen über ein Dropdown-Menü aufgerufen und von den meisten Lesern als Anker verwendet werden.
// Lesezeichen können auch numerische Werte für Gliederungsebenen haben,
// Gliederungseinträge auf niedrigerer Ebene aktivieren, um untergeordnete Einträge auf höherer Ebene zu verbergen, wenn sie im Reader reduziert werden.
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
BookmarksOutlineLevelCollection outlineLevels = pdfSaveOptions.OutlineOptions.BookmarksOutlineLevels;

outlineLevels.Add("Bookmark 1", 1);
outlineLevels.Add("Bookmark 2", 2);
outlineLevels.Add("Bookmark 3", 3);

Assert.AreEqual(3, outlineLevels.Count);
Assert.True(outlineLevels.Contains("Bookmark 1"));
Assert.AreEqual(1, outlineLevels[0]);
Assert.AreEqual(2, outlineLevels["Bookmark 2"]);
Assert.AreEqual(2, outlineLevels.IndexOfKey("Bookmark 3"));

// Wir können zwei Elemente entfernen, sodass nur noch die Bezeichnung der Gliederungsebene für „Lesezeichen 1“ übrig bleibt.
outlineLevels.RemoveAt(2);
outlineLevels.Remove("Bookmark 2");

// Es gibt neun Gliederungsebenen. Ihre Nummerierung wird während des Speichervorgangs optimiert.
// In diesem Fall werden die Ebenen "5" und "9" zu "2" und "3".
outlineLevels.Add("Bookmark 2", 5);
outlineLevels.Add("Bookmark 3", 9);

doc.Save(ArtifactsDir + "BookmarksOutlineLevelCollection.BookmarkLevels.pdf", pdfSaveOptions);

// Durch das Leeren dieser Sammlung werden die Lesezeichen beibehalten und alle auf derselben Gliederungsebene platziert.
outlineLevels.Clear();
```

### Siehe auch

* class [BookmarksOutlineLevelCollection](../)
* namensraum [Aspose.Words.Saving](../../bookmarksoutlinelevelcollection/)
* Montage [Aspose.Words](../../../)


