---
title: LoadOptions.ResourceLoadingCallback
second_title: Référence de l'API Aspose.Words pour .NET
description: LoadOptions propriété. Permet de contrôler le chargement des ressources externes images feuilles de style lorsquun document est importé depuis HTML MHTML.
type: docs
weight: 140
url: /fr/net/aspose.words.loading/loadoptions/resourceloadingcallback/
---
## LoadOptions.ResourceLoadingCallback property

Permet de contrôler le chargement des ressources externes (images, feuilles de style) lorsqu'un document est importé depuis HTML, MHTML.

```csharp
public IResourceLoadingCallback ResourceLoadingCallback { get; set; }
```

### Exemples

Montre comment gérer les ressources externes lors du chargement de documents HTML.

```csharp
{
    LoadOptions loadOptions = new LoadOptions();
    loadOptions.ResourceLoadingCallback = new HtmlLinkedResourceLoadingCallback();

    // Lorsque nous chargeons le document, notre rappel gère les ressources liées telles que les feuilles de style CSS et les images.
    Document doc = new Document(MyDir + "Images.html", loadOptions);
    doc.Save(ArtifactsDir + "LoadOptions.LoadOptionsCallback.pdf");
}

/// <summary>
/// Imprime les noms de fichiers de toutes les feuilles de style externes et remplace toutes les images d'un document html chargé.
/// </summary>
private class HtmlLinkedResourceLoadingCallback : IResourceLoadingCallback
{
    public ResourceLoadingAction ResourceLoading(ResourceLoadingArgs args)
    {
        switch (args.ResourceType)
        {
            case ResourceType.CssStyleSheet:
                Console.WriteLine($"External CSS Stylesheet found upon loading: {args.OriginalUri}");
                return ResourceLoadingAction.Default;
            case ResourceType.Image:
                Console.WriteLine($"External Image found upon loading: {args.OriginalUri}");

                const string newImageFilename = "Logo.jpg";
                Console.WriteLine($"\tImage will be substituted with: {newImageFilename}");

                Image newImage = Image.FromFile(ImageDir + newImageFilename);

                ImageConverter converter = new ImageConverter();
                byte[] imageBytes = (byte[])converter.ConvertTo(newImage, typeof(byte[]));
                args.SetData(imageBytes);

                return ResourceLoadingAction.UserProvided;
        }

        return ResourceLoadingAction.Default;
    }
}
```

### Voir également

* interface [IResourceLoadingCallback](../../iresourceloadingcallback/)
* class [LoadOptions](../)
* espace de noms [Aspose.Words.Loading](../../loadoptions/)
* Assemblée [Aspose.Words](../../../)


