---
title: PsSaveOptions.UseBookFoldPrintingSettings
second_title: Aspose.Words per .NET API Reference
description: PsSaveOptions proprietà. Ottiene o imposta un valore booleano che indica se il documento deve essere salvato utilizzando un layout di stampa opuscolo se specificato tramiteMultiplePages .
type: docs
weight: 30
url: /it/net/aspose.words.saving/pssaveoptions/usebookfoldprintingsettings/
---
## PsSaveOptions.UseBookFoldPrintingSettings property

Ottiene o imposta un valore booleano che indica se il documento deve essere salvato utilizzando un layout di stampa opuscolo, se specificato tramite[`MultiplePages`](../../../aspose.words/pagesetup/multiplepages/) .

```csharp
public bool UseBookFoldPrintingSettings { get; set; }
```

### Osservazioni

Se questa opzione è specificata,[`PageSet`](../../fixedpagesaveoptions/pageset/) viene ignorato durante il salvataggio. Questo comportamento corrisponde a MS Word. Se le impostazioni di stampa della piegatura libro non sono specificate nelle impostazioni di pagina, questa opzione non avrà effetto.

### Esempi

Mostra come salvare un documento nel formato Postscript sotto forma di piega a libro.

```csharp
Document doc = new Document(MyDir + "Paragraphs.docx");

// Crea un oggetto "PsSaveOptions" che possiamo passare al metodo "Save" del documento
// per modificare il modo in cui quel metodo converte il documento in PostScript.
// Imposta la proprietà "UseBookFoldPrintingSettings" su "true" per disporre i contenuti
// nel documento Postscript di output in un modo che ci aiuti a farne un opuscolo.
// Imposta la proprietà "UseBookFoldPrintingSettings" su "false" per salvare il documento normalmente.
PsSaveOptions saveOptions = new PsSaveOptions
{
    SaveFormat = SaveFormat.Ps,
    UseBookFoldPrintingSettings = renderTextAsBookFold
};

// Se stiamo visualizzando il documento come un opuscolo, dobbiamo impostare "MultiplePages"
// proprietà degli oggetti di impostazione della pagina di tutte le sezioni in "MultiplePagesType.BookFoldPrinting".
foreach (Section s in doc.Sections)
{
    s.PageSetup.MultiplePages = MultiplePagesType.BookFoldPrinting;
}

// Una volta stampato questo documento su entrambi i lati delle pagine, possiamo piegare tutte le pagine al centro contemporaneamente,
// e il contenuto si allineerà in modo da creare un opuscolo.
doc.Save(ArtifactsDir + "PsSaveOptions.UseBookFoldPrintingSettings.ps", saveOptions);
```

### Guarda anche

* class [PsSaveOptions](../)
* spazio dei nomi [Aspose.Words.Saving](../../pssaveoptions/)
* assemblea [Aspose.Words](../../../)


