---
title: Interface IPageLayoutCallback
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Layout.IPageLayoutCallback koppel. Implementieren Sie diese Schnittstelle wenn Sie möchten dass Ihre eigene benutzerdefinierte Methode während des Erstellens und Renderns des Seitenlayoutmodells aufgerufen wird.
type: docs
weight: 3110
url: /de/net/aspose.words.layout/ipagelayoutcallback/
---
## IPageLayoutCallback interface

Implementieren Sie diese Schnittstelle, wenn Sie möchten, dass Ihre eigene benutzerdefinierte Methode während des Erstellens und Renderns des Seitenlayoutmodells aufgerufen wird.

```csharp
public interface IPageLayoutCallback
```

## Methoden

| Name | Beschreibung |
| --- | --- |
| [Notify](../../aspose.words.layout/ipagelayoutcallback/notify/)(PageLayoutCallbackArgs) | Dies wird aufgerufen, um über den Layouterstellungs- und Renderfortschritt zu informieren. |

### Bemerkungen

Der Hauptzweck dieser Schnittstelle besteht darin, dem Anwendungscode zu ermöglichen, den Erstellungsprozess abzubrechen.

Es ist möglich, ein Seitenlayoutmodell für nur wenige Seiten am Anfang des Dokuments zu erstellen, dann den Vorgang abzubrechen und nur das zu rendern, was bereits erstellt wurde.

Beachten Sie jedoch, dass die Rendering-Ergebnisse möglicherweise nicht mit dem übereinstimmen, was für jede Seite gerendert würde, wenn der Prozess abgeschlossen wäre.

Diese Technik funktioniert möglicherweise nicht für jedes Dokument oder schlägt vollständig fehl.

### Beispiele

Zeigt, wie Layoutänderungen mit einem Layout-Callback nachverfolgt werden.

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
/// Benachrichtigt uns, wenn wir das Dokument in einem festen Seitenformat speichern
/// und rendert eine Seite, auf der wir einen Seitenumbruch zu einem Bild im lokalen Dateisystem durchführen.
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

### Siehe auch

* property [Callback](../layoutoptions/callback/)
* namensraum [Aspose.Words.Layout](../../aspose.words.layout/)
* Montage [Aspose.Words](../../)


