---
title: Enum PdfTextCompression
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Saving.PdfTextCompression enum. Specifica un tipo di compressione applicato a tutto il contenuto del file PDF eccetto le immagini.
type: docs
weight: 5250
url: /it/net/aspose.words.saving/pdftextcompression/
---
## PdfTextCompression enumeration

Specifica un tipo di compressione applicato a tutto il contenuto del file PDF eccetto le immagini.

```csharp
public enum PdfTextCompression
```

### I valori

| Nome | Valore | Descrizione |
| --- | --- | --- |
| None | `0` | Nessuna compressione. |
| Flate | `1` | Compressione flate (ZIP). |

### Esempi

Mostra come applicare la compressione del testo durante il salvataggio di un documento in PDF.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

for (int i = 0; i < 100; i++)
    builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, " +
                    "sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");

// Crea un oggetto "PdfSaveOptions" che possiamo passare al metodo "Save" del documento
// per modificare il modo in cui quel metodo converte il documento in .PDF.
PdfSaveOptions options = new PdfSaveOptions();

// Imposta la proprietà "TextCompression" su "PdfTextCompression.None" per non applicarne
// compressione in testo quando salviamo il documento in PDF.
// Imposta la proprietà "TextCompression" su "PdfTextCompression.Flate" per applicare la compressione ZIP
// in testo quando salviamo il documento in PDF. Più grande è il documento, maggiore sarà l'impatto che questo avrà.
options.TextCompression = pdfTextCompression;

doc.Save(ArtifactsDir + "PdfSaveOptions.TextCompression.pdf", options);
```

### Guarda anche

* spazio dei nomi [Aspose.Words.Saving](../../aspose.words.saving/)
* assemblea [Aspose.Words](../../)


