---
title: Interface IPageLayoutCallback
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.Layout.IPageLayoutCallback interface. Implémentez cette interface si vous souhaitez que votre propre méthode personnalisée soit appelée lors de la construction et du rendu du modèle de mise en page.
type: docs
weight: 3110
url: /fr/net/aspose.words.layout/ipagelayoutcallback/
---
## IPageLayoutCallback interface

Implémentez cette interface si vous souhaitez que votre propre méthode personnalisée soit appelée lors de la construction et du rendu du modèle de mise en page.

```csharp
public interface IPageLayoutCallback
```

## Méthodes

| Nom | La description |
| --- | --- |
| [Notify](../../aspose.words.layout/ipagelayoutcallback/notify/)(PageLayoutCallbackArgs) | Ceci est appelé pour notifier la construction de la mise en page et la progression du rendu. |

### Remarques

L'utilisation principale de cette interface est de permettre au code de l'application d'abandonner le processus de génération.

Il est possible de créer un modèle de mise en page pour seulement quelques pages au début du document, puis d'abandonner le processus et de ne rendre que ce qui a déjà été construit.

Notez, cependant, que les résultats du rendu peuvent ne pas correspondre à ce qui serait rendu pour chaque page si le processus était terminé.

Cette technique peut ne pas fonctionner pour tous les documents ou échouer complètement.

### Exemples

Montre comment suivre les modifications de mise en page avec un rappel de mise en page.

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
/// Nous avertit lorsque nous enregistrons le document dans un format de page fixe
/// et affiche une page sur laquelle nous effectuons une redistribution de page vers une image dans le système de fichiers local.
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

### Voir également

* property [Callback](../layoutoptions/callback/)
* espace de noms [Aspose.Words.Layout](../../aspose.words.layout/)
* Assemblée [Aspose.Words](../../)


