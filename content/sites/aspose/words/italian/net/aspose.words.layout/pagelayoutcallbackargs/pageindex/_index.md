---
title: PageLayoutCallbackArgs.PageIndex
second_title: Aspose.Words per .NET API Reference
description: PageLayoutCallbackArgs proprietà. Ottiene lindice in base 0 della pagina nel documento a cui si riferisce questo evento. Restituisce un valore negativo se non è presente alcuna pagina associata o se la pagina è stata rimossa durante il reflow.
type: docs
weight: 30
url: /it/net/aspose.words.layout/pagelayoutcallbackargs/pageindex/
---
## PageLayoutCallbackArgs.PageIndex property

Ottiene l'indice in base 0 della pagina nel documento a cui si riferisce questo evento. Restituisce un valore negativo se non è presente alcuna pagina associata o se la pagina è stata rimossa durante il reflow.

```csharp
public int PageIndex { get; }
```

### Esempi

Mostra come tenere traccia delle modifiche al layout con una richiamata del layout.

```csharp
[Test]
public void PageLayoutCallback()
{
    Document doc = new Document();
    doc.BuiltInDocumentProperties.Title = "My Document";

    DocumentBuilder builder = new DocumentBuilder(doc);
    builder.Writeln("Hello world!");

    doc.LayoutOptions.Callback = new RenderPageLayoutCallback();
    doc.UpdatePageLayout();

    doc.Save(ArtifactsDir + "Layout.PageLayoutCallback.pdf");
}

/// <summary>
/// Avvisa quando salviamo il documento in un formato pagina fisso
/// ed esegue il rendering di una pagina su cui eseguiamo un riflusso della pagina in un'immagine nel file system locale.
/// </summary>
private class RenderPageLayoutCallback : IPageLayoutCallback
{
    public void Notify(PageLayoutCallbackArgs a)
    {
        switch (a.Event)
        {
            case PageLayoutEvent.PartReflowFinished:
                NotifyPartFinished(a);
                break;
            case PageLayoutEvent.ConversionFinished:
                NotifyConversionFinished(a);
                break;
        }
    }

    private void NotifyPartFinished(PageLayoutCallbackArgs a)
    {
        Console.WriteLine($"Part at page {a.PageIndex + 1} reflow.");
        RenderPage(a, a.PageIndex);
    }

    private void NotifyConversionFinished(PageLayoutCallbackArgs a)
    {
        Console.WriteLine($"Document \"{a.Document.BuiltInDocumentProperties.Title}\" converted to page format.");
    }

    private void RenderPage(PageLayoutCallbackArgs a, int pageIndex)
    {
        ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png) { PageSet = new PageSet(pageIndex) };

        using (FileStream stream =
            new FileStream(ArtifactsDir + $@"PageLayoutCallback.page-{pageIndex + 1} {++mNum}.png",
                FileMode.Create))
            a.Document.Save(stream, saveOptions);
    }

    private int mNum;
}
```

### Guarda anche

* class [PageLayoutCallbackArgs](../)
* spazio dei nomi [Aspose.Words.Layout](../../pagelayoutcallbackargs/)
* assemblea [Aspose.Words](../../../)


