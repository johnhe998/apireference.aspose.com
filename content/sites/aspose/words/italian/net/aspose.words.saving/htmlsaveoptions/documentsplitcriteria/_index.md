---
title: HtmlSaveOptions.DocumentSplitCriteria
second_title: Aspose.Words per .NET API Reference
description: HtmlSaveOptions proprietà. Specifica come dividere il documento durante il salvataggio inHtml oEpub formato. Limpostazione predefinita èNone per HTML e HeadingParagraph per EPUB.
type: docs
weight: 80
url: /it/net/aspose.words.saving/htmlsaveoptions/documentsplitcriteria/
---
## HtmlSaveOptions.DocumentSplitCriteria property

Specifica come dividere il documento durante il salvataggio inHtml oEpub formato. L'impostazione predefinita èNone per HTML e HeadingParagraph per EPUB.

```csharp
public DocumentSplitCriteria DocumentSplitCriteria { get; set; }
```

### Osservazioni

Normalmente vorresti che un documento venisse salvato in HTML come un singolo file. Ma in alcuni casi è preferibile dividere l'output in più pagine HTML più piccole. Quando si salva in formato HTML, queste pagine verranno inviate a singoli file o flussi. Quando si salva in formato EPUB, verranno incorporati nei pacchetti corrispondenti.

Non è possibile dividere un documento durante il salvataggio in formato MHTML.

### Esempi

Mostra come utilizzare una codifica specifica durante il salvataggio di un documento in .epub.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// Usa un oggetto SaveOptions per specificare la codifica per un documento che salveremo.
HtmlSaveOptions saveOptions = new HtmlSaveOptions();
saveOptions.SaveFormat = SaveFormat.Epub;
saveOptions.Encoding = Encoding.UTF8;

// Per impostazione predefinita, un documento di output .epub avrà tutto il suo contenuto in una parte HTML.
// Un criterio diviso ci consente di segmentare il documento in più parti HTML.
// Definiremo i criteri per dividere il documento in paragrafi di intestazione.
// Questo è utile per i lettori che non possono leggere file HTML più significativi di una dimensione specifica.
saveOptions.DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph;

// Specifica che vogliamo esportare le proprietà del documento.
saveOptions.ExportDocumentProperties = true;

doc.Save(ArtifactsDir + "HtmlSaveOptions.Doc2EpubSaveOptions.epub", saveOptions);
```

### Guarda anche

* enum [DocumentSplitCriteria](../../documentsplitcriteria/)
* class [HtmlSaveOptions](../)
* spazio dei nomi [Aspose.Words.Saving](../../htmlsaveoptions/)
* assemblea [Aspose.Words](../../../)


