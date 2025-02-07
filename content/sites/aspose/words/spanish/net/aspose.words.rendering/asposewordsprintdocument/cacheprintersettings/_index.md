---
title: AsposeWordsPrintDocument.CachePrinterSettings
second_title: Referencia de API de Aspose.Words para .NET
description: AsposeWordsPrintDocument método. Lee y almacena en caché algunos campos dePrinterSettings para reducir el tiempo de impresión.
type: docs
weight: 20
url: /es/net/aspose.words.rendering/asposewordsprintdocument/cacheprintersettings/
---
## AsposeWordsPrintDocument.CachePrinterSettings method

Lee y almacena en caché algunos campos dePrinterSettings para reducir el tiempo de impresión.

```csharp
public void CachePrinterSettings()
```

### Observaciones

Este método se llama antes de que comience la impresión si no se ejecutó previamente.

### Ejemplos

Muestra cómo seleccionar un rango de páginas y una impresora para imprimir el documento y luego mostrar una vista previa de impresión.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

PrintPreviewDialog previewDlg = new PrintPreviewDialog();

// Llame al método "Mostrar" para que el formulario de vista previa de impresión se muestre en la parte superior.
previewDlg.Show();

// Inicialice el cuadro de diálogo de impresión con el número de páginas del documento.
PrintDialog printDlg = new PrintDialog();
printDlg.AllowSomePages = true;
printDlg.PrinterSettings.MinimumPage = 1;
printDlg.PrinterSettings.MaximumPage = doc.PageCount;
printDlg.PrinterSettings.FromPage = 1;
printDlg.PrinterSettings.ToPage = doc.PageCount;

if (printDlg.ShowDialog() != DialogResult.OK)
    return;

// Crear la implementación "Aspose.Words" del documento de impresión .NET,
// y luego pase la configuración de la impresora desde el cuadro de diálogo.
AsposeWordsPrintDocument awPrintDoc = new AsposeWordsPrintDocument(doc);
awPrintDoc.PrinterSettings = printDlg.PrinterSettings;

// Utilice el método "CachePrinterSettings" para reducir el tiempo de la primera llamada del método "Imprimir".
awPrintDoc.CachePrinterSettings();

// Llame a los métodos "Ocultar" y luego a "Invalidar vista previa" para que la vista previa de impresión se muestre en la parte superior.
previewDlg.Hide();
previewDlg.PrintPreviewControl.InvalidatePreview();

// Pase el documento de impresión "Aspose.Words" al cuadro de diálogo Vista previa de impresión de .NET.
previewDlg.Document = awPrintDoc;

previewDlg.ShowDialog();
```

### Ver también

* class [AsposeWordsPrintDocument](../)
* espacio de nombres [Aspose.Words.Rendering](../../asposewordsprintdocument/)
* asamblea [Aspose.Words](../../../)


