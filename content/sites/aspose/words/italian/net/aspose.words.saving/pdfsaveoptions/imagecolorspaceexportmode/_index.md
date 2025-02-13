---
title: PdfSaveOptions.ImageColorSpaceExportMode
second_title: Aspose.Words per .NET API Reference
description: PdfSaveOptions proprietà. Specifica come verrà selezionato lo spazio colore per le immagini nel documento PDF.
type: docs
weight: 160
url: /it/net/aspose.words.saving/pdfsaveoptions/imagecolorspaceexportmode/
---
## PdfSaveOptions.ImageColorSpaceExportMode property

Specifica come verrà selezionato lo spazio colore per le immagini nel documento PDF.

```csharp
public PdfImageColorSpaceExportMode ImageColorSpaceExportMode { get; set; }
```

### Osservazioni

Il valore predefinito èAuto .

SeSimpleCmyk il valore è specificato, [`ImageCompression`](../imagecompression/) l'opzione viene ignorata e La compressione Flate viene utilizzata per tutte le immagini nel documento.

SimpleCmyk il valore non è supportato durante il salvataggio in PDF/A. Auto verrà invece utilizzato il valore.

### Esempi

Mostra come impostare uno spazio colore diverso per le immagini in un documento mentre lo esportiamo in PDF.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Jpeg image:");
builder.InsertImage(ImageDir + "Logo.jpg");
builder.InsertParagraph();
builder.Writeln("Png image:");
builder.InsertImage(ImageDir + "Transparent background logo.png");

// Crea un oggetto "PdfSaveOptions" che possiamo passare al metodo "Save" del documento
// per modificare il modo in cui quel metodo converte il documento in .PDF.
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();

// Imposta la proprietà "ImageColorSpaceExportMode" su "PdfImageColorSpaceExportMode.Auto" per ottenere Aspose.Words su
// seleziona automaticamente lo spazio colore per le immagini nel documento che converte in PDF.
// Nella maggior parte dei casi, lo spazio colore sarà RGB.
// Imposta la proprietà "ImageColorSpaceExportMode" su "PdfImageColorSpaceExportMode.SimpleCmyk"
// per utilizzare lo spazio colore CMYK per tutte le immagini nel PDF salvato.
// Aspose.Words applicherà anche la compressione Flate a tutte le immagini e ignorerà il valore della proprietà "ImageCompression".
pdfSaveOptions.ImageColorSpaceExportMode = pdfImageColorSpaceExportMode;

doc.Save(ArtifactsDir + "PdfSaveOptions.ImageColorSpaceExportMode.pdf", pdfSaveOptions);
```

### Guarda anche

* enum [PdfImageColorSpaceExportMode](../../pdfimagecolorspaceexportmode/)
* class [PdfSaveOptions](../)
* spazio dei nomi [Aspose.Words.Saving](../../pdfsaveoptions/)
* assemblea [Aspose.Words](../../../)


