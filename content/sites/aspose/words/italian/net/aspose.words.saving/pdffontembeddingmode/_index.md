---
title: Enum PdfFontEmbeddingMode
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Saving.PdfFontEmbeddingMode enum. Specifica come Aspose.Words deve incorporare i caratteri.
type: docs
weight: 5190
url: /it/net/aspose.words.saving/pdffontembeddingmode/
---
## PdfFontEmbeddingMode enumeration

Specifica come Aspose.Words deve incorporare i caratteri.

```csharp
public enum PdfFontEmbeddingMode
```

### I valori

| Nome | Valore | Descrizione |
| --- | --- | --- |
| EmbedAll | `0` | Aspose.Words incorpora tutti i caratteri. |
| EmbedNonstandard | `1` | Aspose.Words incorpora tutti i caratteri ad eccezione dei caratteri Windows standard Arial e Times New Roman. Solo i caratteri Arial e Times New Roman sono interessati in questa modalità poiché MS Word non incorpora solo questi caratteri durante il salvataggio del documento in PDF. |
| EmbedNone | `2` | Aspose.Words non incorpora alcun tipo di carattere. |

### Esempi

Mostra come impostare Aspose.Words per saltare l'incorporamento di font Arial e Times New Roman in un documento PDF.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// "Arial" è un carattere standard e "Courier New" è un carattere non standard.
builder.Font.Name = "Arial";
builder.Writeln("Hello world!");
builder.Font.Name = "Courier New";
builder.Writeln("The quick brown fox jumps over the lazy dog.");

// Crea un oggetto "PdfSaveOptions" che possiamo passare al metodo "Save" del documento
// per modificare il modo in cui quel metodo converte il documento in .PDF.
PdfSaveOptions options = new PdfSaveOptions();

// Imposta la proprietà "EmbedFullFonts" su "true" per incorporare ogni glifo di ogni carattere incorporato nel PDF di output.
options.EmbedFullFonts = true;

// Imposta la proprietà "FontEmbeddingMode" su "EmbedAll" per incorporare tutti i caratteri nel PDF di output.
// Imposta la proprietà "FontEmbeddingMode" su "EmbedNonstandard" per consentire solo l'incorporamento di caratteri non standard nel PDF di output.
// Imposta la proprietà "FontEmbeddingMode" su "EmbedNone" per non incorporare alcun tipo di carattere nel PDF di output.
options.FontEmbeddingMode = pdfFontEmbeddingMode;

doc.Save(ArtifactsDir + "PdfSaveOptions.EmbedWindowsFonts.pdf", options);

switch (pdfFontEmbeddingMode)
{
    case PdfFontEmbeddingMode.EmbedAll:
        Assert.That(1000000, Is.LessThan(new FileInfo(ArtifactsDir + "PdfSaveOptions.EmbedWindowsFonts.pdf").Length));
        break;
    case PdfFontEmbeddingMode.EmbedNonstandard:
        Assert.That(480000, Is.LessThan(new FileInfo(ArtifactsDir + "PdfSaveOptions.EmbedWindowsFonts.pdf").Length));
        break;
    case PdfFontEmbeddingMode.EmbedNone:
        Assert.That(4217, Is.AtLeast(new FileInfo(ArtifactsDir + "PdfSaveOptions.EmbedWindowsFonts.pdf").Length));
        break;
}
```

### Guarda anche

* spazio dei nomi [Aspose.Words.Saving](../../aspose.words.saving/)
* assemblea [Aspose.Words](../../)


