---
title: ResourceSavingArgs.Document
second_title: Référence de l'API Aspose.Words pour .NET
description: ResourceSavingArgs propriété. Obtient lobjet document en cours denregistrement.
type: docs
weight: 10
url: /fr/net/aspose.words.saving/resourcesavingargs/document/
---
## ResourceSavingArgs.Document property

Obtient l'objet document en cours d'enregistrement.

```csharp
public Document Document { get; }
```

### Exemples

Montre comment utiliser un rappel pour suivre les ressources externes créées lors de la conversion d'un document au format HTML.

```csharp
public void ResourceSavingCallback()
{
    Document doc = new Document(MyDir + "Bullet points with alternative font.docx");

    FontSavingCallback callback = new FontSavingCallback();

    HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions
    {
        ResourceSavingCallback = callback
    };

    doc.Save(ArtifactsDir + "HtmlFixedSaveOptions.UsingMachineFonts.html", saveOptions);

    Console.WriteLine(callback.GetText());
}

private class FontSavingCallback : IResourceSavingCallback
{
    /// <summary>
    /// Appelé quand Aspose.Words enregistre une ressource externe dans une page fixe HTML ou SVG.
    /// </summary>
    public void ResourceSaving(ResourceSavingArgs args)
    {
        mText.AppendLine($"Original document URI:\t{args.Document.OriginalFileName}");
        mText.AppendLine($"Resource being saved:\t{args.ResourceFileName}");
        mText.AppendLine($"Full uri after saving:\t{args.ResourceFileUri}\n");
    }

    public string GetText()
    {
        return mText.ToString();
    }

    private readonly StringBuilder mText = new StringBuilder();
}
```

### Voir également

* class [Document](../../../aspose.words/document/)
* class [ResourceSavingArgs](../)
* espace de noms [Aspose.Words.Saving](../../resourcesavingargs/)
* Assemblée [Aspose.Words](../../../)


