---
title: AsposeWordsPrintDocument Class
linktitle: AsposeWordsPrintDocument
articleTitle: AsposeWordsPrintDocument
second_title: Aspose.Words for .NET
description: Aspose.Words.Rendering.AsposeWordsPrintDocument class. Provides a default implementation for printing of a Document within the .NET printing framework in C#.
type: docs
weight: 4500
url: /net/aspose.words.rendering/asposewordsprintdocument/
---
## AsposeWordsPrintDocument class

Provides a default implementation for printing of a [`Document`](../../aspose.words/document/) within the .NET printing framework.

To learn more, visit the [Printing a Document Programmatically or Using Dialogs](https://docs.aspose.com/words/net/print-a-document-programmatically-or-using-dialogs/) documentation article.

```csharp
public class AsposeWordsPrintDocument : PrintDocument
```

## Constructors

| Name | Description |
| --- | --- |
| [AsposeWordsPrintDocument](asposewordsprintdocument/)(*[Document](../../aspose.words/document/)*) | Initializes a new instance of this class. |

## Properties

| Name | Description |
| --- | --- |
| [ColorMode](../../aspose.words.rendering/asposewordsprintdocument/colormode/) { get; set; } | Gets or sets how non-colored pages are printed if the device supports color printing. |
| [ColorPagesPrinted](../../aspose.words.rendering/asposewordsprintdocument/colorpagesprinted/) { get; } | Gets the number of pages printed in color (i.e. with Color set to true). |

## Methods

| Name | Description |
| --- | --- |
| [CachePrinterSettings](../../aspose.words.rendering/asposewordsprintdocument/cacheprintersettings/)() | Reads and caches some fields of PrinterSettings to reduce printing time. |

## Remarks

`AsposeWordsPrintDocument` overrides PrintEventArgs) to print the range of pages that is specified in PrinterSettings.

A single Word document can consist of multiple sections that specify pages with different sizes, orientation and paper trays. `AsposeWordsPrintDocument` overrides QueryPageSettingsEventArgs) to properly select paper size, orientation and paper source when printing a Word document.

Microsoft Word stores printer specific values for paper trays in a Word document and therefore, only printing on the same printer model as the one that was selected when the user specified the paper trays will result in printing from the correct trays. If you print a document on a different printer, then most likely the default paper tray will be used, not the trays specified in the document.

### See Also

* namespace [Aspose.Words.Rendering](../../aspose.words.rendering/)
* assembly [Aspose.Words](../../)
