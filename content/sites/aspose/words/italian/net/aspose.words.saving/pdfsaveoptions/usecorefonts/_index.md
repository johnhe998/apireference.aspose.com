---
title: PdfSaveOptions.UseCoreFonts
second_title: Aspose.Words per .NET API Reference
description: PdfSaveOptions proprietà. Ottiene o imposta un valore che determina se sostituire o meno i font TrueType Arial Times New Roman Courier New e Symbol con i font PDF Type 1 di base.
type: docs
weight: 280
url: /it/net/aspose.words.saving/pdfsaveoptions/usecorefonts/
---
## PdfSaveOptions.UseCoreFonts property

Ottiene o imposta un valore che determina se sostituire o meno i font TrueType Arial, Times New Roman, Courier New e Symbol con i font PDF Type 1 di base.

```csharp
public bool UseCoreFonts { get; set; }
```

### Osservazioni

Il valore predefinito è`falso` . Quando questo valore è impostato su`VERO` I font Arial, Times New Roman, Courier New e Symbol vengono sostituiti nel documento PDF con il font Type 1 di base corrispondente.

I caratteri PDF principali, o le relative metriche dei caratteri e caratteri sostitutivi adeguati, devono essere disponibili per qualsiasi applicazione visualizzatore PDF .

Questa impostazione funziona solo per il testo nella codifica ANSI (Windows-1252). Il testo non ANSI verrà scritto con il carattere TrueType incorporato indipendentemente da questa impostazione.

La conformità PDF/A e PDF/UA richiede che tutti i caratteri siano incorporati.`falso` il valore verrà utilizzato automaticamente durante il salvataggio in PDF/A e PDF/UA.

I caratteri principali non sono supportati durante il salvataggio in formato PDF 2.0.`falso`il valore verrà utilizzato automaticamente durante il salvataggio in PDF 2.0.

Questa opzione ha quindi una priorità maggiore[`FontEmbeddingMode`](../fontembeddingmode/) opzione.

### Esempi

Mostra come abilitare/disabilitare la sostituzione del carattere PDF di tipo 1.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Name = "Arial";
builder.Writeln("Hello world!");
builder.Font.Name = "Courier New";
builder.Writeln("The quick brown fox jumps over the lazy dog.");

// Crea un oggetto "PdfSaveOptions" che possiamo passare al metodo "Save" del documento
// per modificare il modo in cui quel metodo converte il documento in .PDF.
PdfSaveOptions options = new PdfSaveOptions();

// Imposta la proprietà "UseCoreFonts" su "true" per sostituire alcuni caratteri,
// inclusi i due caratteri nel nostro documento, con i loro equivalenti PDF di tipo 1.
// Imposta la proprietà "UseCoreFonts" su "false" per non applicare i font PDF Type 1.
options.UseCoreFonts = useCoreFonts;

doc.Save(ArtifactsDir + "PdfSaveOptions.EmbedCoreFonts.pdf", options);

if (useCoreFonts)
    Assert.That(3000, Is.AtLeast(new FileInfo(ArtifactsDir + "PdfSaveOptions.EmbedCoreFonts.pdf").Length));
else
    Assert.That(30000, Is.LessThan(new FileInfo(ArtifactsDir + "PdfSaveOptions.EmbedCoreFonts.pdf").Length));
```

### Guarda anche

* class [PdfSaveOptions](../)
* spazio dei nomi [Aspose.Words.Saving](../../pdfsaveoptions/)
* assemblea [Aspose.Words](../../../)


