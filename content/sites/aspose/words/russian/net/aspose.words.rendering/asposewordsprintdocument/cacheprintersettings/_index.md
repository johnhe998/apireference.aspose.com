---
title: AsposeWordsPrintDocument.CachePrinterSettings
second_title: Справочник по API Aspose.Words для .NET
description: AsposeWordsPrintDocument метод. Читает и кэширует некоторые поляPrinterSettings для сокращения времени печати.
type: docs
weight: 20
url: /ru/net/aspose.words.rendering/asposewordsprintdocument/cacheprintersettings/
---
## AsposeWordsPrintDocument.CachePrinterSettings method

Читает и кэширует некоторые поляPrinterSettings для сокращения времени печати.

```csharp
public void CachePrinterSettings()
```

### Примечания

Этот метод вызывается перед началом печати, если он не был выполнен ранее.

### Примеры

Показывает, как выбрать диапазон страниц и принтер для печати документа, а затем вызвать предварительный просмотр печати.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

PrintPreviewDialog previewDlg = new PrintPreviewDialog();

// Вызовите метод "Show", чтобы форма предварительного просмотра печати отображалась сверху.
previewDlg.Show();

// Инициализируем диалог печати количеством страниц в документе.
PrintDialog printDlg = new PrintDialog();
printDlg.AllowSomePages = true;
printDlg.PrinterSettings.MinimumPage = 1;
printDlg.PrinterSettings.MaximumPage = doc.PageCount;
printDlg.PrinterSettings.FromPage = 1;
printDlg.PrinterSettings.ToPage = doc.PageCount;

if (printDlg.ShowDialog() != DialogResult.OK)
    return;

// Создаем реализацию "Aspose.Words" документа печати .NET,
// и затем передать настройки принтера из диалогового окна.
AsposeWordsPrintDocument awPrintDoc = new AsposeWordsPrintDocument(doc);
awPrintDoc.PrinterSettings = printDlg.PrinterSettings;

// Используйте метод "CachePrinterSettings", чтобы сократить время первого вызова метода "Печать".
awPrintDoc.CachePrinterSettings();

// Вызываем метод «Скрыть», а затем метод «InvalidatePreview», чтобы предварительный просмотр отображался сверху.
previewDlg.Hide();
previewDlg.PrintPreviewControl.InvalidatePreview();

// Передайте документ печати "Aspose.Words" в диалоговое окно .NET Print Preview.
previewDlg.Document = awPrintDoc;

previewDlg.ShowDialog();
```

### Смотрите также

* class [AsposeWordsPrintDocument](../)
* пространство имен [Aspose.Words.Rendering](../../asposewordsprintdocument/)
* сборка [Aspose.Words](../../../)


