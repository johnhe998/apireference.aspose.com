---
title: AsposeWordsPrintDocument.CachePrinterSettings
second_title: Aspose.Words for .NET API Referansı
description: AsposeWordsPrintDocument yöntem. Şunun bazı alanlarını okur ve önbelleğe alırPrinterSettings yazdırma süresini azaltmak için.
type: docs
weight: 20
url: /tr/net/aspose.words.rendering/asposewordsprintdocument/cacheprintersettings/
---
## AsposeWordsPrintDocument.CachePrinterSettings method

Şunun bazı alanlarını okur ve önbelleğe alır:PrinterSettings yazdırma süresini azaltmak için.

```csharp
public void CachePrinterSettings()
```

### Notlar

Bu yöntem, daha önce yürütülmediyse, yazdırma başlamadan önce çağrılır.

### Örnekler

Belgeyi yazdırmak için bir sayfa aralığı ve yazıcının nasıl seçileceğini ve ardından bir baskı önizlemesinin nasıl getirileceğini gösterir.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

PrintPreviewDialog previewDlg = new PrintPreviewDialog();

// Baskı önizleme formunun en üstte gösterilmesini sağlamak için "Show" yöntemini çağırın.
previewDlg.Show();

// Belgedeki sayfa sayısıyla Yazdırma İletişim Kutusunu başlatın.
PrintDialog printDlg = new PrintDialog();
printDlg.AllowSomePages = true;
printDlg.PrinterSettings.MinimumPage = 1;
printDlg.PrinterSettings.MaximumPage = doc.PageCount;
printDlg.PrinterSettings.FromPage = 1;
printDlg.PrinterSettings.ToPage = doc.PageCount;

if (printDlg.ShowDialog() != DialogResult.OK)
    return;

// .NET yazdırma belgesinin "Aspose.Words" uygulamasını oluşturun,
// ve ardından iletişim kutusundan yazıcı ayarlarını geçirin.
AsposeWordsPrintDocument awPrintDoc = new AsposeWordsPrintDocument(doc);
awPrintDoc.PrinterSettings = printDlg.PrinterSettings;

// "Yazdır" yönteminin ilk çağrısının süresini azaltmak için "CachePrinterSettings" yöntemini kullanın.
awPrintDoc.CachePrinterSettings();

// Baskı önizlemenin en üstte gösterilmesini sağlamak için "Gizle" ve ardından "InvalidatePreview" yöntemlerini çağırın.
previewDlg.Hide();
previewDlg.PrintPreviewControl.InvalidatePreview();

// "Aspose.Words" yazdırma belgesini .NET Baskı Önizleme iletişim kutusuna iletin.
previewDlg.Document = awPrintDoc;

previewDlg.ShowDialog();
```

### Ayrıca bakınız

* class [AsposeWordsPrintDocument](../)
* ad alanı [Aspose.Words.Rendering](../../asposewordsprintdocument/)
* toplantı [Aspose.Words](../../../)


