---
title: AsposeWordsPrintDocument.CachePrinterSettings
second_title: Aspose.Words für .NET-API-Referenz
description: AsposeWordsPrintDocument methode. Liest und speichert einige Felder vonPrinterSettings um die Druckzeit zu reduzieren.
type: docs
weight: 20
url: /de/net/aspose.words.rendering/asposewordsprintdocument/cacheprintersettings/
---
## AsposeWordsPrintDocument.CachePrinterSettings method

Liest und speichert einige Felder vonPrinterSettings um die Druckzeit zu reduzieren.

```csharp
public void CachePrinterSettings()
```

### Bemerkungen

Diese Methode wird vor Beginn des Druckens aufgerufen, wenn sie nicht vorher ausgeführt wurde.

### Beispiele

Zeigt, wie Sie einen Seitenbereich und einen Drucker zum Drucken des Dokuments auswählen und dann eine Druckvorschau aufrufen.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

PrintPreviewDialog previewDlg = new PrintPreviewDialog();

// Rufen Sie die "Show"-Methode auf, damit das Druckvorschau-Formular oben angezeigt wird.
previewDlg.Show();

// Den Druckdialog mit der Anzahl der Seiten im Dokument initialisieren.
PrintDialog printDlg = new PrintDialog();
printDlg.AllowSomePages = true;
printDlg.PrinterSettings.MinimumPage = 1;
printDlg.PrinterSettings.MaximumPage = doc.PageCount;
printDlg.PrinterSettings.FromPage = 1;
printDlg.PrinterSettings.ToPage = doc.PageCount;

if (printDlg.ShowDialog() != DialogResult.OK)
    return;

// Erstellen Sie die "Aspose.Words"-Implementierung des .NET-Druckdokuments,
// und dann die Druckereinstellungen aus dem Dialog übergeben.
AsposeWordsPrintDocument awPrintDoc = new AsposeWordsPrintDocument(doc);
awPrintDoc.PrinterSettings = printDlg.PrinterSettings;

// Verwenden Sie die Methode "CachePrinterSettings", um die Zeit des ersten Aufrufs der Methode "Print" zu reduzieren.
awPrintDoc.CachePrinterSettings();

// Rufen Sie die "Hide"- und dann die "InvalidatePreview"-Methode auf, damit die Druckvorschau oben angezeigt wird.
previewDlg.Hide();
previewDlg.PrintPreviewControl.InvalidatePreview();

// Übergeben Sie das Druckdokument "Aspose.Words" an das .NET-Druckvorschau-Dialogfeld.
previewDlg.Document = awPrintDoc;

previewDlg.ShowDialog();
```

### Siehe auch

* class [AsposeWordsPrintDocument](../)
* namensraum [Aspose.Words.Rendering](../../asposewordsprintdocument/)
* Montage [Aspose.Words](../../../)


