---
title: PdfSaveOptions.ZoomBehavior
second_title: Aspose.Words per .NET API Reference
description: PdfSaveOptions proprietà. Ottiene o imposta un valore che determina il tipo di zoom da applicare quando un documento viene aperto con un visualizzatore PDF.
type: docs
weight: 290
url: /it/net/aspose.words.saving/pdfsaveoptions/zoombehavior/
---
## PdfSaveOptions.ZoomBehavior property

Ottiene o imposta un valore che determina il tipo di zoom da applicare quando un documento viene aperto con un visualizzatore PDF.

```csharp
public PdfZoomBehavior ZoomBehavior { get; set; }
```

### Osservazioni

Il valore predefinito èNone , ovvero non viene applicato alcun adattamento.

### Esempi

Mostra come impostare lo zoom predefinito applicato da un lettore all'apertura di un documento PDF sottoposto a rendering.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

// Crea un oggetto "PdfSaveOptions" che possiamo passare al metodo "Save" del documento
// per modificare il modo in cui quel metodo converte il documento in .PDF.
// Imposta la proprietà "ZoomBehavior" su "PdfZoomBehavior.ZoomFactor" per far sì che un lettore PDF
// applica un fattore di zoom in percentuale quando apriamo il documento con esso.
// Imposta la proprietà "ZoomFactor" su "25" per dare al fattore di zoom un valore del 25%.
PdfSaveOptions options = new PdfSaveOptions
{
    ZoomBehavior = PdfZoomBehavior.ZoomFactor,
    ZoomFactor = 25
};

// Quando apriamo questo documento utilizzando un lettore come Adobe Acrobat, vedremo il documento ridimensionato a 1/4 della sua dimensione effettiva.
doc.Save(ArtifactsDir + "PdfSaveOptions.ZoomBehaviour.pdf", options);
```

### Guarda anche

* enum [PdfZoomBehavior](../../pdfzoombehavior/)
* class [PdfSaveOptions](../)
* spazio dei nomi [Aspose.Words.Saving](../../pdfsaveoptions/)
* assemblea [Aspose.Words](../../../)


