---
title: PdfSaveOptions.CreateNoteHyperlinks
second_title: Aspose.Words per .NET API Reference
description: PdfSaveOptions proprietà. Specifica se convertire i riferimenti a piè di pagina/nota di chiusura nella storia di testo principale in collegamenti ipertestuali attivi. Quando si fa clic il collegamento ipertestuale porterà alla nota a piè di pagina/nota di chiusura corrispondente. Limpostazione predefinita èfalso .
type: docs
weight: 40
url: /it/net/aspose.words.saving/pdfsaveoptions/createnotehyperlinks/
---
## PdfSaveOptions.CreateNoteHyperlinks property

Specifica se convertire i riferimenti a piè di pagina/nota di chiusura nella storia di testo principale in collegamenti ipertestuali attivi. Quando si fa clic, il collegamento ipertestuale porterà alla nota a piè di pagina/nota di chiusura corrispondente. L'impostazione predefinita è`falso` .

```csharp
public bool CreateNoteHyperlinks { get; set; }
```

### Esempi

Mostra come fare in modo che le note a piè di pagina e le note di chiusura funzionino come collegamenti ipertestuali.

```csharp
Document doc = new Document(MyDir + "Footnotes and endnotes.docx");

// Crea un oggetto "PdfSaveOptions" che possiamo passare al metodo "Save" del documento
// per modificare il modo in cui quel metodo converte il documento in .PDF.
PdfSaveOptions options = new PdfSaveOptions();

// Imposta la proprietà "CreateNoteHyperlinks" su "true" per trasformare tutti i simboli di note a piè di pagina/note di chiusura
// nel testo fungono da link che, cliccando, ci portano alle rispettive note a piè di pagina/note di chiusura.
// Imposta la proprietà "CreateNoteHyperlinks" su "false" in modo che i simboli di note a piè di pagina/note di chiusura non si colleghino a nulla.
options.CreateNoteHyperlinks = createNoteHyperlinks;

doc.Save(ArtifactsDir + "PdfSaveOptions.NoteHyperlinks.pdf", options);
```

### Guarda anche

* class [PdfSaveOptions](../)
* spazio dei nomi [Aspose.Words.Saving](../../pdfsaveoptions/)
* assemblea [Aspose.Words](../../../)


