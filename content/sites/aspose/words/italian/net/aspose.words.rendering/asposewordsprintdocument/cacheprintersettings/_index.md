---
title: AsposeWordsPrintDocument.CachePrinterSettings
second_title: Aspose.Words per .NET API Reference
description: AsposeWordsPrintDocument metodo. Legge e memorizza nella cache alcuni campi diPrinterSettings per ridurre i tempi di stampa.
type: docs
weight: 20
url: /it/net/aspose.words.rendering/asposewordsprintdocument/cacheprintersettings/
---
## AsposeWordsPrintDocument.CachePrinterSettings method

Legge e memorizza nella cache alcuni campi diPrinterSettings per ridurre i tempi di stampa.

```csharp
public void CachePrinterSettings()
```

### Osservazioni

Questo metodo viene chiamato prima dell'inizio della stampa se non è stato eseguito in precedenza.

### Esempi

Mostra come selezionare un intervallo di pagine e una stampante con cui stampare il documento e quindi visualizzare un'anteprima di stampa.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

PrintPreviewDialog previewDlg = new PrintPreviewDialog();

// Chiama il metodo "Mostra" per visualizzare il modulo di anteprima di stampa in primo piano.
previewDlg.Show();

// Inizializza la finestra di dialogo Stampa con il numero di pagine del documento.
PrintDialog printDlg = new PrintDialog();
printDlg.AllowSomePages = true;
printDlg.PrinterSettings.MinimumPage = 1;
printDlg.PrinterSettings.MaximumPage = doc.PageCount;
printDlg.PrinterSettings.FromPage = 1;
printDlg.PrinterSettings.ToPage = doc.PageCount;

if (printDlg.ShowDialog() != DialogResult.OK)
    return;

// Crea l'implementazione "Aspose.Words" del documento di stampa .NET,
// e quindi passa le impostazioni della stampante dalla finestra di dialogo.
AsposeWordsPrintDocument awPrintDoc = new AsposeWordsPrintDocument(doc);
awPrintDoc.PrinterSettings = printDlg.PrinterSettings;

// Utilizzare il metodo "CachePrinterSettings" per ridurre il tempo della prima chiamata del metodo "Print".
awPrintDoc.CachePrinterSettings();

// Chiama i metodi "Nascondi" e poi "InvalidatePreview" per visualizzare l'anteprima di stampa in primo piano.
previewDlg.Hide();
previewDlg.PrintPreviewControl.InvalidatePreview();

// Passa il documento di stampa "Aspose.Words" alla finestra di dialogo Anteprima di stampa .NET.
previewDlg.Document = awPrintDoc;

previewDlg.ShowDialog();
```

### Guarda anche

* class [AsposeWordsPrintDocument](../)
* spazio dei nomi [Aspose.Words.Rendering](../../asposewordsprintdocument/)
* assemblea [Aspose.Words](../../../)


