---
title: OutlineOptions.BookmarksOutlineLevels
second_title: Aspose.Words per .NET API Reference
description: OutlineOptions proprietà. Consente di specificare il livello di struttura dei segnalibri individuali.
type: docs
weight: 20
url: /it/net/aspose.words.saving/outlineoptions/bookmarksoutlinelevels/
---
## OutlineOptions.BookmarksOutlineLevels property

Consente di specificare il livello di struttura dei segnalibri individuali.

```csharp
public BookmarksOutlineLevelCollection BookmarksOutlineLevels { get; }
```

### Osservazioni

Se il livello del segnalibro non è specificato in questa raccolta, allora[`DefaultBookmarksOutlineLevel`](../defaultbookmarksoutlinelevel/) viene utilizzato il valore.

### Esempi

Mostra come impostare i livelli di struttura per i segnalibri.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserisce un segnalibro con un altro segnalibro nidificato al suo interno.
builder.StartBookmark("Bookmark 1");
builder.Writeln("Text inside Bookmark 1.");

builder.StartBookmark("Bookmark 2");
builder.Writeln("Text inside Bookmark 1 and 2.");
builder.EndBookmark("Bookmark 2");

builder.Writeln("Text inside Bookmark 1.");
builder.EndBookmark("Bookmark 1");

// Inserisci un altro segnalibro.
builder.StartBookmark("Bookmark 3");
builder.Writeln("Text inside Bookmark 3.");
builder.EndBookmark("Bookmark 3");

// Quando si salva in .pdf, è possibile accedere ai segnalibri tramite un menu a discesa e utilizzarli come ancoraggi dalla maggior parte dei lettori.
// I segnalibri possono anche avere valori numerici per i livelli di struttura,
// abilita le voci della struttura di livello inferiore per nascondere le voci secondarie di livello superiore quando vengono compresse nel lettore.
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

// Possiamo rimuovere due elementi in modo che rimanga solo la designazione del livello di struttura per "Segnalibro 1".
outlineLevels.RemoveAt(2);
outlineLevels.Remove("Bookmark 2");

// Ci sono nove livelli di struttura. La loro numerazione sarà ottimizzata durante l'operazione di salvataggio.
// In questo caso, i livelli "5" e "9" diventeranno "2" e "3".
outlineLevels.Add("Bookmark 2", 5);
outlineLevels.Add("Bookmark 3", 9);

doc.Save(ArtifactsDir + "BookmarksOutlineLevelCollection.BookmarkLevels.pdf", pdfSaveOptions);

// Lo svuotamento di questa raccolta conserverà i segnalibri e li metterà tutti sullo stesso livello di struttura.
outlineLevels.Clear();
```

### Guarda anche

* class [BookmarksOutlineLevelCollection](../../bookmarksoutlinelevelcollection/)
* class [OutlineOptions](../)
* spazio dei nomi [Aspose.Words.Saving](../../outlineoptions/)
* assemblea [Aspose.Words](../../../)


