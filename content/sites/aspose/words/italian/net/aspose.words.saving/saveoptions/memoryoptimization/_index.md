---
title: SaveOptions.MemoryOptimization
second_title: Aspose.Words per .NET API Reference
description: SaveOptions proprietà. Ottiene o imposta il valore che determina se eseguire lottimizzazione della memoria prima di salvare il documento. Il valore predefinito per questa proprietà è falso .
type: docs
weight: 110
url: /it/net/aspose.words.saving/saveoptions/memoryoptimization/
---
## SaveOptions.MemoryOptimization property

Ottiene o imposta il valore che determina se eseguire l'ottimizzazione della memoria prima di salvare il documento. Il valore predefinito per questa proprietà è **falso** .

```csharp
public bool MemoryOptimization { get; set; }
```

### Osservazioni

L'impostazione di questa opzione su true può ridurre significativamente il consumo di memoria salvando documenti di grandi dimensioni al costo di un risparmio di tempo più lento.

### Esempi

Mostra un'opzione per ottimizzare il consumo di memoria durante il rendering di documenti di grandi dimensioni in PDF.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// Crea un oggetto "PdfSaveOptions" che possiamo passare al metodo "Save" del documento
// per modificare il modo in cui quel metodo converte il documento in .PDF.
SaveOptions saveOptions = SaveOptions.CreateSaveOptions(SaveFormat.Pdf);

// Imposta la proprietà "MemoryOptimization" su "true" per ridurre l'ingombro di memoria delle operazioni di salvataggio di documenti di grandi dimensioni
// a costo di aumentare la durata dell'operazione.
// Imposta la proprietà "MemoryOptimization" su "false" per salvare normalmente il documento come PDF.
saveOptions.MemoryOptimization = memoryOptimization;

doc.Save(ArtifactsDir + "PdfSaveOptions.MemoryOptimization.pdf", saveOptions);
```

### Guarda anche

* class [SaveOptions](../)
* spazio dei nomi [Aspose.Words.Saving](../../saveoptions/)
* assemblea [Aspose.Words](../../../)


