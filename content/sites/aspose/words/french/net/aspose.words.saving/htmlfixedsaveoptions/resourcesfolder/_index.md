---
title: HtmlFixedSaveOptions.ResourcesFolder
second_title: Référence de l'API Aspose.Words pour .NET
description: HtmlFixedSaveOptions propriété. Spécifie le dossier physique dans lequel les ressources images polices css sont enregistrées lors de lexportation dun document au format Html. La valeur par défaut estnul .
type: docs
weight: 140
url: /fr/net/aspose.words.saving/htmlfixedsaveoptions/resourcesfolder/
---
## HtmlFixedSaveOptions.ResourcesFolder property

Spécifie le dossier physique dans lequel les ressources (images, polices, css) sont enregistrées lors de l'exportation d'un document au format Html. La valeur par défaut est`nul` .

```csharp
public string ResourcesFolder { get; set; }
```

### Remarques

N'a d'effet que si[`ExportEmbeddedImages`](../exportembeddedimages/) propriété est fausse.

Lorsque vous enregistrez un[`Document`](../../../aspose.words/document/) au format Html, Aspose.Words doit enregistrer toutes les images incorporées dans le document en tant que fichiers autonomes.`ResourcesFolder` vous permet de spécifier où les images seront enregistrées et[`ResourcesFolderAlias`](../resourcesfolderalias/) permet de spécifier comment les URI des images seront construites.

Si vous enregistrez un document dans un fichier et fournissez un nom de fichier, Aspose.Words, par défaut, enregistre les images the dans le même dossier où le fichier de document est enregistré. Utilisation`ResourcesFolder` pour remplacer ce comportement.

Si vous enregistrez un document dans un flux, Aspose.Words n'a pas de dossier où enregistrer les images, mais doit toujours enregistrer les images quelque part. Dans ce cas, vous devez spécifier un dossier accessible en utilisant le`ResourcesFolder` propriété

### Exemples

Montre comment utiliser un rappel pour imprimer les URI des ressources externes créées lors de la conversion d'un document en HTML.

```csharp
public void HtmlFixedResourceFolder()
{
    Document doc = new Document(MyDir + "Rendering.docx");

    ResourceUriPrinter callback = new ResourceUriPrinter();

    HtmlFixedSaveOptions options = new HtmlFixedSaveOptions
    {
        SaveFormat = SaveFormat.HtmlFixed,
        ExportEmbeddedImages = false,
        ResourcesFolder = ArtifactsDir + "HtmlFixedResourceFolder",
        ResourcesFolderAlias = ArtifactsDir + "HtmlFixedResourceFolderAlias",
        ShowPageBorder = false,
        ResourceSavingCallback = callback
    };

    // Un dossier spécifié par ResourcesFolderAlias contiendra les ressources au lieu de ResourcesFolder.
    // Nous devons nous assurer que le dossier existe avant que les flux puissent y mettre leurs ressources.
    Directory.CreateDirectory(options.ResourcesFolderAlias);

    doc.Save(ArtifactsDir + "HtmlFixedSaveOptions.HtmlFixedResourceFolder.html", options);

    Console.WriteLine(callback.GetText());

    string[] resourceFiles = Directory.GetFiles(ArtifactsDir + "HtmlFixedResourceFolderAlias");

    Assert.False(Directory.Exists(ArtifactsDir + "HtmlFixedResourceFolder"));
    Assert.AreEqual(6, resourceFiles.Count(f => f.EndsWith(".jpeg") || f.EndsWith(".png") || f.EndsWith(".css")));
}

/// <summary>
/// Compte et imprime les URI des ressources contenues par lorsqu'elles sont converties en HTML fixe.
/// </summary>
private class ResourceUriPrinter : IResourceSavingCallback
{
    void IResourceSavingCallback.ResourceSaving(ResourceSavingArgs args)
    {
        // Si nous définissons un alias de dossier dans l'objet SaveOptions, nous pourrons l'imprimer à partir d'ici.
        mText.AppendLine($"Resource #{++mSavedResourceCount} \"{args.ResourceFileName}\"");

        string extension = Path.GetExtension(args.ResourceFileName);
        switch (extension)
        {
            case ".ttf":
            case ".woff":
            {
                // Par défaut, 'ResourceFileUri' utilise le dossier système pour les polices.
                // Pour éviter des problèmes sur d'autres plates-formes, vous devez spécifier explicitement le chemin des polices.
                args.ResourceFileUri = ArtifactsDir + Path.DirectorySeparatorChar + args.ResourceFileName;
                break;
            }
        }

        mText.AppendLine("\t" + args.ResourceFileUri);

        // Si nous avons spécifié un dossier dans la propriété "ResourcesFolderAlias",
        // nous devrons également rediriger chaque flux pour mettre sa ressource dans ce dossier.
        args.ResourceStream = new FileStream(args.ResourceFileUri, FileMode.Create);
        args.KeepResourceStreamOpen = false;
    }

    public string GetText()
    {
        return mText.ToString();
    }

    private int mSavedResourceCount;
    private readonly StringBuilder mText = new StringBuilder();
}
```

### Voir également

* class [HtmlFixedSaveOptions](../)
* espace de noms [Aspose.Words.Saving](../../htmlfixedsaveoptions/)
* Assemblée [Aspose.Words](../../../)


