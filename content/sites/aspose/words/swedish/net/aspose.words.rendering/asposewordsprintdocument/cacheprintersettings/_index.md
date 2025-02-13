---
title: AsposeWordsPrintDocument.CachePrinterSettings
second_title: Aspose.Words för .NET API Referens
description: AsposeWordsPrintDocument metod. Läser och cachar vissa fält avPrinterSettings för att minska utskriftstiden.
type: docs
weight: 20
url: /sv/net/aspose.words.rendering/asposewordsprintdocument/cacheprintersettings/
---
## AsposeWordsPrintDocument.CachePrinterSettings method

Läser och cachar vissa fält avPrinterSettings för att minska utskriftstiden.

```csharp
public void CachePrinterSettings()
```

### Anmärkningar

Denna metod anropas innan utskriften startar om den inte utfördes tidigare.

### Exempel

Visar hur du väljer ett sidintervall och en skrivare att skriva ut dokumentet med och sedan tar fram en förhandsgranskning.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

PrintPreviewDialog previewDlg = new PrintPreviewDialog();

// Anropa "Visa"-metoden för att få förhandsgranskningsformuläret att visas överst.
previewDlg.Show();

// Initiera utskriftsdialogrutan med antalet sidor i dokumentet.
PrintDialog printDlg = new PrintDialog();
printDlg.AllowSomePages = true;
printDlg.PrinterSettings.MinimumPage = 1;
printDlg.PrinterSettings.MaximumPage = doc.PageCount;
printDlg.PrinterSettings.FromPage = 1;
printDlg.PrinterSettings.ToPage = doc.PageCount;

if (printDlg.ShowDialog() != DialogResult.OK)
    return;

// Skapa "Aspose.Words"-implementeringen av .NET-skrivdokumentet,
// och skicka sedan skrivarinställningarna från dialogrutan.
AsposeWordsPrintDocument awPrintDoc = new AsposeWordsPrintDocument(doc);
awPrintDoc.PrinterSettings = printDlg.PrinterSettings;

// Använd metoden "CachePrinterSettings" för att minska tiden för det första anropet av metoden "Skriv ut".
awPrintDoc.CachePrinterSettings();

// Anropa "Hide" och sedan "InvalidatePreview"-metoderna för att få förhandsgranskningen att visas överst.
previewDlg.Hide();
previewDlg.PrintPreviewControl.InvalidatePreview();

// Skicka "Aspose.Words" utskriftsdokumentet till .NET Print Preview-dialogrutan.
previewDlg.Document = awPrintDoc;

previewDlg.ShowDialog();
```

### Se även

* class [AsposeWordsPrintDocument](../)
* namnutrymme [Aspose.Words.Rendering](../../asposewordsprintdocument/)
* hopsättning [Aspose.Words](../../../)


