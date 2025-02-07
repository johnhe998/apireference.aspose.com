---
title: Class OutlineOptions
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Saving.OutlineOptions classe. Consente di specificare le opzioni del contorno.
type: docs
weight: 5080
url: /it/net/aspose.words.saving/outlineoptions/
---
## OutlineOptions class

Consente di specificare le opzioni del contorno.

```csharp
public class OutlineOptions
```

## Costruttori

| Nome | Descrizione |
| --- | --- |
| [OutlineOptions](outlineoptions/)() | Default_Costruttore |

## Proprietà

| Nome | Descrizione |
| --- | --- |
| [BookmarksOutlineLevels](../../aspose.words.saving/outlineoptions/bookmarksoutlinelevels/) { get; } | Consente di specificare il livello di struttura dei segnalibri individuali. |
| [CreateMissingOutlineLevels](../../aspose.words.saving/outlineoptions/createmissingoutlinelevels/) { get; set; } | Ottiene o imposta un valore che determina se creare o meno livelli di struttura mancanti quando il documento viene esportato . |
| [CreateOutlinesForHeadingsInTables](../../aspose.words.saving/outlineoptions/createoutlinesforheadingsintables/) { get; set; } | Specifica se creare o meno profili per le intestazioni (paragrafi formattati con gli stili di intestazione) all'interno delle tabelle. |
| [DefaultBookmarksOutlineLevel](../../aspose.words.saving/outlineoptions/defaultbookmarksoutlinelevel/) { get; set; } | Specifica il livello predefinito nella struttura del documento in cui visualizzare i segnalibri di Word. |
| [ExpandedOutlineLevels](../../aspose.words.saving/outlineoptions/expandedoutlinelevels/) { get; set; } | Specifica quanti livelli nella struttura del documento mostrare espansi quando il file viene visualizzato. |
| [HeadingsOutlineLevels](../../aspose.words.saving/outlineoptions/headingsoutlinelevels/) { get; set; } | Specifica quanti livelli di intestazioni (paragrafi formattati con gli stili di intestazione) includere nella struttura del documento . |

### Esempi

Mostra per elaborare i segnalibri nelle intestazioni/piè di pagina in un documento di cui stiamo effettuando il rendering in PDF.

```csharp
Document doc = new Document(MyDir + "Bookmarks in headers and footers.docx");

// Crea un oggetto "PdfSaveOptions" che possiamo passare al metodo "Save" del documento
// per modificare il modo in cui quel metodo converte il documento in .PDF.
PdfSaveOptions saveOptions = new PdfSaveOptions();

// Imposta la proprietà "PageMode" su "PdfPageMode.UseOutlines" per visualizzare il riquadro di navigazione della struttura nel PDF di output.
saveOptions.PageMode = PdfPageMode.UseOutlines;

// Imposta la proprietà "DefaultBookmarksOutlineLevel" su "1" per visualizzare tutto
// segnalibri al primo livello della struttura nel PDF di output.
saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;

// Imposta la proprietà "HeaderFooterBookmarksExportMode" su "HeaderFooterBookmarksExportMode.None" su
// non esporta i segnalibri che si trovano all'interno di intestazioni/piè di pagina.
// Imposta la proprietà "HeaderFooterBookmarksExportMode" su "HeaderFooterBookmarksExportMode.First" su
// esporta solo i segnalibri nell'intestazione/piè di pagina della prima sezione.
// Imposta la proprietà "HeaderFooterBookmarksExportMode" su "HeaderFooterBookmarksExportMode.All" su
// esporta i segnalibri che si trovano in tutte le intestazioni/piè di pagina.
saveOptions.HeaderFooterBookmarksExportMode = headerFooterBookmarksExportMode;

doc.Save(ArtifactsDir + "PdfSaveOptions.HeaderFooterBookmarksExportMode.pdf", saveOptions);
```

### Guarda anche

* spazio dei nomi [Aspose.Words.Saving](../../aspose.words.saving/)
* assemblea [Aspose.Words](../../)


