---
title: Enum ColorMode
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Saving.ColorMode enum. Specifica come vengono visualizzati i colori.
type: docs
weight: 4600
url: /it/net/aspose.words.saving/colormode/
---
## ColorMode enumeration

Specifica come vengono visualizzati i colori.

```csharp
public enum ColorMode
```

### I valori

| Nome | Valore | Descrizione |
| --- | --- | --- |
| Normal | `0` | Rendering con colori non modificati. |
| Grayscale | `1` | Rendering con colori in una gamma di sfumature di grigio dal bianco al nero. |

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

* spazio dei nomi [Aspose.Words.Saving](../../aspose.words.saving/)
* assemblea [Aspose.Words](../../)


