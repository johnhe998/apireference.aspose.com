---
title: PageInfo.GetDotNetPaperSize
second_title: Aspose.Words für .NET-API-Referenz
description: PageInfo methode. Ruft die abPaperSize Objekt das zum Drucken der von diesem repräsentierten Seite geeignet istPageInfo .
type: docs
weight: 70
url: /de/net/aspose.words.rendering/pageinfo/getdotnetpapersize/
---
## PageInfo.GetDotNetPaperSize method

Ruft die abPaperSize Objekt, das zum Drucken der von diesem repräsentierten Seite geeignet ist[`PageInfo`](../) .

```csharp
public PaperSize GetDotNetPaperSize(PaperSizeCollection paperSizes)
```

| Parameter | Typ | Beschreibung |
| --- | --- | --- |
| paperSizes | PaperSizeCollection | Verfügbare Papierformate. |

### Rückgabewert

Ein Objekt, das Sie im .NET-Druckframework verwenden können, um das Papierformat anzugeben.

### Beispiele

Zeigt, wie das Drucken von Aspose.Words-Dokumenten angepasst wird.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

    MyPrintDocument printDoc = new MyPrintDocument(doc);
    printDoc.PrinterSettings.PrintRange = System.Drawing.Printing.PrintRange.SomePages;
    printDoc.PrinterSettings.FromPage = 1;
    printDoc.PrinterSettings.ToPage = 1;

    printDoc.Print();
}

/// <summary>
/// Wählt beim Drucken eine geeignete Papiergröße, Ausrichtung und Papierkassette aus.
/// </summary>
public class MyPrintDocument : PrintDocument
{
    public MyPrintDocument(Document document)
    {
        mDocument = document;
    }

    /// <summary>
    /// Initialisiert den Bereich der zu druckenden Seiten gemäß der Benutzerauswahl.
    /// </summary>
    protected override void OnBeginPrint(PrintEventArgs e)
    {
        base.OnBeginPrint(e);

        switch (PrinterSettings.PrintRange)
        {
            case System.Drawing.Printing.PrintRange.AllPages:
                mCurrentPage = 1;
                mPageTo = mDocument.PageCount;
                break;
            case System.Drawing.Printing.PrintRange.SomePages:
                mCurrentPage = PrinterSettings.FromPage;
                mPageTo = PrinterSettings.ToPage;
                break;
            default:
                throw new InvalidOperationException("Unsupported print range.");
        }
    }

    /// <summary>
    /// Wird aufgerufen, bevor jede Seite gedruckt wird. 
    /// </summary>
    protected override void OnQueryPageSettings(QueryPageSettingsEventArgs e)
    {
        base.OnQueryPageSettings(e);

        // Ein einzelnes Microsoft Word-Dokument kann mehrere Abschnitte haben, die Seiten mit unterschiedlichen Größen angeben, 
        // Ausrichtungen und Papierfächer. Das .NET-Druckframework ruft diesen Code zuvor auf 
        // Jede Seite wird gedruckt, was uns die Möglichkeit gibt, anzugeben, wie die aktuelle Seite gedruckt werden soll.
        PageInfo pageInfo = mDocument.GetPageInfo(mCurrentPage - 1);
        e.PageSettings.PaperSize = pageInfo.GetDotNetPaperSize(PrinterSettings.PaperSizes);

        // Microsoft Word speichert die Papierquelle (Druckfach) für jeden Abschnitt als druckerspezifischen Wert.
        // Um den korrekten Fachwert zu erhalten, müssen Sie die "RawKind"-Eigenschaft verwenden, die Ihr Drucker zurückgeben sollte.
        e.PageSettings.PaperSource.RawKind = pageInfo.PaperTray;
        e.PageSettings.Landscape = pageInfo.Landscape;
    }

    /// <summary>
    /// Wird für jede Seite aufgerufen, um sie zum Drucken zu rendern. 
    /// </summary>
    protected override void OnPrintPage(PrintPageEventArgs e)
    {
        base.OnPrintPage(e);

        // Aspose.Words-Rendering-Engine erstellt eine Seite, die vom Ursprung (x = 0, y = 0) des Papiers gezeichnet wird.
        // Es wird einen harten Rand im Drucker geben, der jede Seite rendert. Wir müssen diese harte Marge ausgleichen.
        float hardOffsetX, hardOffsetY;

        // Im Folgenden finden Sie zwei Möglichkeiten, einen harten Rand festzulegen.
        if (e.PageSettings != null && e.PageSettings.HardMarginX != 0 && e.PageSettings.HardMarginY != 0)
        {
            // 1 - Über die Eigenschaft "PageSettings".
            hardOffsetX = e.PageSettings.HardMarginX;
            hardOffsetY = e.PageSettings.HardMarginY;
        }
        else
        {
            // 2 - Verwenden unserer eigenen Werte, wenn die Eigenschaft "PageSettings" nicht verfügbar ist.
            hardOffsetX = 20;
            hardOffsetY = 20;
        }

        mDocument.RenderToScale(mCurrentPage, e.Graphics, -hardOffsetX, -hardOffsetY, 1.0f);

        mCurrentPage++;
        e.HasMorePages = mCurrentPage <= mPageTo;
    }

    private readonly Document mDocument;
    private int mCurrentPage;
    private int mPageTo;
}
```

### Siehe auch

* class [PageInfo](../)
* namensraum [Aspose.Words.Rendering](../../pageinfo/)
* Montage [Aspose.Words](../../../)


