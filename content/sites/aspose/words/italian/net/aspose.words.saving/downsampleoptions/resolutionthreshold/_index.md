---
title: DownsampleOptions.ResolutionThreshold
second_title: Aspose.Words per .NET API Reference
description: DownsampleOptions proprietà. Specifica la risoluzione di soglia in pixel per pollice. Se la risoluzione di unimmagine nel documento è inferiore al valore di soglia lalgoritmo di downsampling non verrà applicato. Un valore di 0 significa che il controllo di soglia non è utilizzato e tutte le immagini che possono essere ridotte di dimensioni vengono sottocampionate.
type: docs
weight: 40
url: /it/net/aspose.words.saving/downsampleoptions/resolutionthreshold/
---
## DownsampleOptions.ResolutionThreshold property

Specifica la risoluzione di soglia in pixel per pollice. Se la risoluzione di un'immagine nel documento è inferiore al valore di soglia, l'algoritmo di downsampling non verrà applicato. Un valore di 0 significa che il controllo di soglia non è utilizzato e tutte le immagini che possono essere ridotte di dimensioni vengono sottocampionate.

```csharp
public int ResolutionThreshold { get; set; }
```

### Osservazioni

Il valore predefinito è 0.

### Esempi

Mostra come modificare la risoluzione delle immagini nel documento PDF.

```csharp
Document doc = new Document(MyDir + "Images.docx");

// Crea un oggetto "PdfSaveOptions" che possiamo passare al metodo "Save" del documento
// per modificare il modo in cui quel metodo converte il documento in .PDF.
PdfSaveOptions options = new PdfSaveOptions();

// Per impostazione predefinita, Aspose.Words esegue il downsampling di tutte le immagini in un documento che salviamo in PDF a 220 ppi.
Assert.True(options.DownsampleOptions.DownsampleImages);
Assert.AreEqual(220, options.DownsampleOptions.Resolution);
Assert.AreEqual(0, options.DownsampleOptions.ResolutionThreshold);

doc.Save(ArtifactsDir + "PdfSaveOptions.DownsampleOptions.Default.pdf", options);

// Imposta la proprietà "Risoluzione" su "36" per eseguire il downsamp di tutte le immagini a 36 ppi.
options.DownsampleOptions.Resolution = 36;

// Imposta la proprietà "ResolutionThreshold" per applicare solo il downsampling
// immagini con una risoluzione superiore a 128 ppi.
options.DownsampleOptions.ResolutionThreshold = 128;

// Solo le prime due immagini del documento verranno sottocampionate in questa fase.
doc.Save(ArtifactsDir + "PdfSaveOptions.DownsampleOptions.LowerResolution.pdf", options);
```

### Guarda anche

* class [DownsampleOptions](../)
* spazio dei nomi [Aspose.Words.Saving](../../downsampleoptions/)
* assemblea [Aspose.Words](../../../)


