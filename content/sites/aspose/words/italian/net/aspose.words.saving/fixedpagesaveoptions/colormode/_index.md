---
title: FixedPageSaveOptions.ColorMode
second_title: Aspose.Words per .NET API Reference
description: FixedPageSaveOptions proprietà. Ottiene o imposta un valore che determina la modalità di rendering dei colori.
type: docs
weight: 10
url: /it/net/aspose.words.saving/fixedpagesaveoptions/colormode/
---
## FixedPageSaveOptions.ColorMode property

Ottiene o imposta un valore che determina la modalità di rendering dei colori.

```csharp
public ColorMode ColorMode { get; set; }
```

### Osservazioni

Il valore predefinito èNormal .

### Esempi

Mostra come cambiare il colore dell'immagine con la proprietà delle opzioni di salvataggio.

```csharp
Document doc = new Document(MyDir + "Images.docx");

// Crea un oggetto "PdfSaveOptions" che possiamo passare al metodo "Save" del documento
// per modificare il modo in cui quel metodo converte il documento in .PDF.
// Imposta la proprietà "ColorMode" su "Grayscale" per eseguire il rendering di tutte le immagini del documento in bianco e nero.
// La dimensione del documento di output potrebbe essere maggiore con questa impostazione.
// Imposta la proprietà "ColorMode" su "Normal" per rendere tutte le immagini a colori.
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions { ColorMode = colorMode };

doc.Save(ArtifactsDir + "PdfSaveOptions.ColorRendering.pdf", pdfSaveOptions);
```

### Guarda anche

* enum [ColorMode](../../colormode/)
* class [FixedPageSaveOptions](../)
* spazio dei nomi [Aspose.Words.Saving](../../fixedpagesaveoptions/)
* assemblea [Aspose.Words](../../../)


