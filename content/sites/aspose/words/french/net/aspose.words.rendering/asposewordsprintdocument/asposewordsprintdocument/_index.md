---
title: AsposeWordsPrintDocument.AsposeWordsPrintDocument
second_title: Référence de l'API Aspose.Words pour .NET
description: AsposeWordsPrintDocument constructeur. Initialise une nouvelle instance de cette classe.
type: docs
weight: 10
url: /fr/net/aspose.words.rendering/asposewordsprintdocument/asposewordsprintdocument/
---
## AsposeWordsPrintDocument constructor

Initialise une nouvelle instance de cette classe.

```csharp
public AsposeWordsPrintDocument(Document document)
```

| Paramètre | Taper | La description |
| --- | --- | --- |
| document | Document | Le document à imprimer. |

### Exemples

Montre comment sélectionner une plage de pages et une imprimante avec laquelle imprimer le document, puis afficher un aperçu avant impression.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

PrintPreviewDialog previewDlg = new PrintPreviewDialog();

// Appelez la méthode "Show" pour que le formulaire d'aperçu avant impression s'affiche en haut.
previewDlg.Show();

// Initialise la boîte de dialogue d'impression avec le nombre de pages du document.
PrintDialog printDlg = new PrintDialog();
printDlg.AllowSomePages = true;
printDlg.PrinterSettings.MinimumPage = 1;
printDlg.PrinterSettings.MaximumPage = doc.PageCount;
printDlg.PrinterSettings.FromPage = 1;
printDlg.PrinterSettings.ToPage = doc.PageCount;

if (printDlg.ShowDialog() != DialogResult.OK)
    return;

// Créer l'implémentation "Aspose.Words" du document d'impression .NET,
// puis passez les paramètres de l'imprimante à partir de la boîte de dialogue.
AsposeWordsPrintDocument awPrintDoc = new AsposeWordsPrintDocument(doc);
awPrintDoc.PrinterSettings = printDlg.PrinterSettings;

// Utilisez la méthode "CachePrinterSettings" pour réduire le temps du premier appel de la méthode "Print".
awPrintDoc.CachePrinterSettings();

// Appelez les méthodes "Hide", puis "InvalidatePreview" pour que l'aperçu avant impression s'affiche en haut.
previewDlg.Hide();
previewDlg.PrintPreviewControl.InvalidatePreview();

// Passez le document d'impression "Aspose.Words" à la boîte de dialogue Aperçu avant impression .NET.
previewDlg.Document = awPrintDoc;

previewDlg.ShowDialog();
```

### Voir également

* class [Document](../../../aspose.words/document/)
* class [AsposeWordsPrintDocument](../)
* espace de noms [Aspose.Words.Rendering](../../asposewordsprintdocument/)
* Assemblée [Aspose.Words](../../../)


