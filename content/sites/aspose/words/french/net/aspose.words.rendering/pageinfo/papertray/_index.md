---
title: PageInfo.PaperTray
second_title: Référence de l'API Aspose.Words pour .NET
description: PageInfo propriété. Obtient le bac à papier bac pour cette page comme spécifié dans le document. La valeur est spécifique à limplémentation imprimante.
type: docs
weight: 40
url: /fr/net/aspose.words.rendering/pageinfo/papertray/
---
## PageInfo.PaperTray property

Obtient le bac à papier (bac) pour cette page comme spécifié dans le document. La valeur est spécifique à l'implémentation (imprimante).

```csharp
public int PaperTray { get; }
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

### Voir également

* class [PageInfo](../)
* espace de noms [Aspose.Words.Rendering](../../pageinfo/)
* Assemblée [Aspose.Words](../../../)


