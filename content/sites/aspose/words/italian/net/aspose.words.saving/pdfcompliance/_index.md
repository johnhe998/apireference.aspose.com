---
title: Enum PdfCompliance
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Saving.PdfCompliance enum. Specifica il livello di conformità agli standard PDF.
type: docs
weight: 5130
url: /it/net/aspose.words.saving/pdfcompliance/
---
## PdfCompliance enumeration

Specifica il livello di conformità agli standard PDF.

```csharp
public enum PdfCompliance
```

### I valori

| Nome | Valore | Descrizione |
| --- | --- | --- |
| Pdf17 | `0` | Il file di output sarà conforme allo standard PDF 1.7 (ISO 32000-1). |
| Pdf20 | `1` | Il file di output sarà conforme allo standard PDF 2.0 (ISO 32000-2). |
| PdfA1a | `2` | Il file di output sarà conforme allo standard PDF/A-1a (ISO 19005-1). Questo livello include tutti i requisiti di PDF/A-1b e richiede inoltre che la struttura del documento sia inclusa (nota anche come "taggata" ), con l'obiettivo di garantire che il contenuto del documento possa essere ricercato e riproposto. |
| PdfA1b | `3` | Il file di output sarà conforme allo standard PDF/A-1b (ISO 19005-1). PDF/A-1b ha l'obiettivo di garantire una riproduzione affidabile dell'aspetto visivo del documento. |
| PdfA2a | `4` | Il file di output sarà conforme allo standard PDF/A-2a (ISO 19005-2). Questo livello include tutti i requisiti di PDF/A-2u e richiede inoltre che la struttura del documento sia inclusa (nota anche come "taggata" ), con l'obiettivo di garantire che il contenuto del documento possa essere ricercato e riproposto. |
| PdfA2u | `5` | Il file di output sarà conforme allo standard PDF/A-2u (ISO 19005-2). PDF/A-2u ha l'obiettivo di preservare l'aspetto visivo statico del documento nel tempo, indipendentemente dagli strumenti e dai sistemi utilizzati per la creazione, l'archiviazione o il rendering dei file. Inoltre, qualsiasi testo contenuto nel documento può essere estratto in modo affidabile come una serie di codepoint Unicode. |
| PdfA4 | `6` | Il file di output sarà conforme allo standard PDF/A-4 (ISO 19005-4:2020). PDF/A-4 ha l'obiettivo di preservare l'aspetto visivo statico del documento nel tempo, indipendentemente dagli strumenti e dai sistemi utilizzati per la creazione , archiviare o eseguire il rendering dei file. Inoltre, qualsiasi testo contenuto nel documento può essere estratto in modo affidabile come una serie di codepoint Unicode. |
| PdfUa1 | `7` | Il file di output sarà conforme allo standard PDF/UA-1 (ISO 14289-1). Lo scopo principale di PDF/UA è definire come rappresentare i documenti elettronici in formato PDF in un modo che consenta al file di essere accessibile. |

### Esempi

Mostra come impostare il livello di conformità agli standard PDF dei documenti PDF salvati.

```csharp
Document doc = new Document(MyDir + "Images.docx");

// Crea un oggetto "PdfSaveOptions" che possiamo passare al metodo "Save" del documento
// per modificare il modo in cui quel metodo converte il documento in .PDF.
// Si noti che alcune PdfSaveOptions sono vietate durante il salvataggio in uno degli standard e risolte automaticamente.
// Usa IWarningCallback per sapere quali opzioni vengono corrette automaticamente.
PdfSaveOptions saveOptions = new PdfSaveOptions();

// Imposta la proprietà "Compliance" su "PdfCompliance.PdfA1b" per conformarsi allo standard "PDF/A-1b",
// che mira a preservare l'aspetto visivo del documento mentre Aspose.Words lo converte in PDF.
// Imposta la proprietà "Compliance" su "PdfCompliance.Pdf17" per conformarsi allo standard "1.7".
// Imposta la proprietà "Compliance" su "PdfCompliance.PdfA1a" per conformarsi allo standard "PDF/A-1a",
// conforme a "PDF/A-1b" oltre a preservare la struttura del documento del documento originale.
// Imposta la proprietà "Compliance" su "PdfCompliance.PdfUa1" per conformarsi allo standard "PDF/UA-1" (ISO 14289-1),
// che mira a definire rappresentare documenti elettronici in PDF che consentano l'accesso al file.
// Ciò aiuta a rendere ricercabili i documenti, ma può aumentare notevolmente le dimensioni di documenti già di grandi dimensioni.
saveOptions.Compliance = pdfCompliance;

doc.Save(ArtifactsDir + "PdfSaveOptions.Compliance.pdf", saveOptions);
```

### Guarda anche

* spazio dei nomi [Aspose.Words.Saving](../../aspose.words.saving/)
* assemblea [Aspose.Words](../../)


