---
title: PageInfo.Landscape
second_title: Référence de l'API Aspose.Words pour .NET
description: PageInfo propriété. Renvoie true si lorientation de page spécifiée dans le document pour cette page est paysage.
type: docs
weight: 20
url: /fr/net/aspose.words.rendering/pageinfo/landscape/
---
## PageInfo.Landscape property

Renvoie true si l'orientation de page spécifiée dans le document pour cette page est paysage.

```csharp
public bool Landscape { get; }
```

### Exemples

Montre comment imprimer des informations sur la taille et l'orientation de la page pour chaque page d'un document Word.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// La première section comporte 2 pages. Nous attribuerons un bac à papier d'imprimante différent à chacun,
// dont le numéro correspondra à un type de source papier. Ces sources et leurs types varieront
// en fonction du pilote d'imprimante installé.
PrinterSettings.PaperSourceCollection paperSources = new PrinterSettings().PaperSources;

doc.FirstSection.PageSetup.FirstPageTray = paperSources[0].RawKind;
doc.FirstSection.PageSetup.OtherPagesTray = paperSources[1].RawKind;

Console.WriteLine("Document \"{0}\" contains {1} pages.", doc.OriginalFileName, doc.PageCount);

float scale = 1.0f;
float dpi = 96;

for (int i = 0; i < doc.PageCount; i++)
{
    // Chaque page a un objet PageInfo, dont l'index est le numéro de la page respective.
    PageInfo pageInfo = doc.GetPageInfo(i);

    // Affiche l'orientation et les dimensions de la page.
    Console.WriteLine($"Page {i + 1}:");
    Console.WriteLine($"\tOrientation:\t{(pageInfo.Landscape ? "Landscape" : "Portrait")}");
    Console.WriteLine($"\tPaper size:\t\t{pageInfo.PaperSize} ({pageInfo.WidthInPoints:F0}x{pageInfo.HeightInPoints:F0}pt)");
    Console.WriteLine($"\tSize in points:\t{pageInfo.SizeInPoints}");
    Console.WriteLine($"\tSize in pixels:\t{pageInfo.GetSizeInPixels(1.0f, 96)} at {scale * 100}% scale, {dpi} dpi");

    // Imprime les informations du bac source.
    Console.WriteLine($"\tTray:\t{pageInfo.PaperTray}");
    PaperSource source = pageInfo.GetSpecifiedPrinterPaperSource(paperSources, paperSources[0]);
    Console.WriteLine($"\tSuitable print source:\t{source.SourceName}, kind: {source.Kind}");
}
```

Montre comment personnaliser l'impression des documents Aspose.Words.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

    MyPrintDocument printDoc = new MyPrintDocument(doc);
    printDoc.PrinterSettings.PrintRange = System.Drawing.Printing.PrintRange.SomePages;
    printDoc.PrinterSettings.FromPage = 1;
    printDoc.PrinterSettings.ToPage = 1;

    printDoc.Print();
}

/// <summary>
/// Sélectionne un format de papier, une orientation et un bac à papier appropriés lors de l'impression.
/// </summary>
public class MyPrintDocument : PrintDocument
{
    public MyPrintDocument(Document document)
    {
        mDocument = document;
    }

    /// <summary>
    /// Initialise la plage de pages à imprimer en fonction de la sélection de l'utilisateur.
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
    /// Appelé avant l'impression de chaque page. 
    /// </summary>
    protected override void OnQueryPageSettings(QueryPageSettingsEventArgs e)
    {
        base.OnQueryPageSettings(e);

        // Un seul document Microsoft Word peut avoir plusieurs sections qui spécifient des pages de tailles différentes, 
        // orientations et bacs à papier. Le framework d'impression .NET appelle ce code avant 
        // chaque page est imprimée, ce qui nous permet de spécifier comment imprimer la page courante.
        PageInfo pageInfo = mDocument.GetPageInfo(mCurrentPage - 1);
        e.PageSettings.PaperSize = pageInfo.GetDotNetPaperSize(PrinterSettings.PaperSizes);

        // Microsoft Word stocke la source de papier (bac de l'imprimante) pour chaque section en tant que valeur spécifique à l'imprimante.
        // Pour obtenir la bonne valeur de bac, vous devrez utiliser la propriété "RawKind", que votre imprimante doit renvoyer.
        e.PageSettings.PaperSource.RawKind = pageInfo.PaperTray;
        e.PageSettings.Landscape = pageInfo.Landscape;
    }

    /// <summary>
    /// Appelé pour chaque page afin de la rendre pour l'impression. 
    /// </summary>
    protected override void OnPrintPage(PrintPageEventArgs e)
    {
        base.OnPrintPage(e);

        // Le moteur de rendu Aspose.Words crée une page dessinée à partir de l'origine (x = 0, y = 0) du papier.
        // Il y aura une marge dure dans l'imprimante, qui rendra chaque page. Nous devons compenser par cette marge dure.
        float hardOffsetX, hardOffsetY;

        // Vous trouverez ci-dessous deux manières de définir une marge ferme.
        if (e.PageSettings != null && e.PageSettings.HardMarginX != 0 && e.PageSettings.HardMarginY != 0)
        {
            // 1 - Via la propriété "PageSettings".
            hardOffsetX = e.PageSettings.HardMarginX;
            hardOffsetY = e.PageSettings.HardMarginY;
        }
        else
        {
            // 2 - En utilisant nos propres valeurs, si la propriété "PageSettings" n'est pas disponible.
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

### Voir également

* class [PageInfo](../)
* espace de noms [Aspose.Words.Rendering](../../pageinfo/)
* Assemblée [Aspose.Words](../../../)


