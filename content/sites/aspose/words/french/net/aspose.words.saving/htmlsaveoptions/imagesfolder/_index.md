---
title: HtmlSaveOptions.ImagesFolder
second_title: Référence de l'API Aspose.Words pour .NET
description: HtmlSaveOptions propriété. Spécifie le dossier physique dans lequel les images sont enregistrées lors de lexportation dun document au format HTML. La valeur par défaut est une chaîne vide.
type: docs
weight: 370
url: /fr/net/aspose.words.saving/htmlsaveoptions/imagesfolder/
---
## HtmlSaveOptions.ImagesFolder property

Spécifie le dossier physique dans lequel les images sont enregistrées lors de l'exportation d'un document au format HTML. La valeur par défaut est une chaîne vide.

```csharp
public string ImagesFolder { get; set; }
```

### Remarques

Lorsque vous enregistrez un[`Document`](../../../aspose.words/document/) au format HTML, Aspose.Words doit enregistrer toutes les images intégrées dans le document en tant que fichiers autonomes.`ImagesFolder` vous permet de spécifier où les images seront enregistrées et[`ImagesFolderAlias`](../imagesfolderalias/) permet de spécifier comment les URI des images seront construites.

Si vous enregistrez un document dans un fichier et fournissez un nom de fichier, Aspose.Words, par défaut, enregistre les images dans le même dossier où le fichier du document est enregistré. Utilisation`ImagesFolder` pour remplacer ce comportement.

Si vous enregistrez un document dans un flux, Aspose.Words n'a pas de dossier où enregistrer les images, mais doit toujours enregistrer les images quelque part. Dans ce cas, vous devez spécifier un dossier accessible dans le`ImagesFolder` propriété ou fournir des flux personnalisés via le[`ImageSavingCallback`](../imagesavingcallback/) gestionnaire d'événements.

Si le dossier spécifié par`ImagesFolder` n'existe pas, il sera créé automatiquement.

[`ResourceFolder`](../resourcefolder/) est un autre moyen de spécifier un dossier dans lequel les images doivent être enregistrées.

### Exemples

Montre comment spécifier le dossier de stockage des images liées après l'enregistrement au format .html.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

string imagesDir = Path.Combine(ArtifactsDir, "SaveHtmlWithOptions");

if (Directory.Exists(imagesDir))
    Directory.Delete(imagesDir, true);

Directory.CreateDirectory(imagesDir);

// Définissez une option pour exporter les champs de formulaire en tant que texte brut au lieu d'éléments d'entrée HTML.
HtmlSaveOptions options = new HtmlSaveOptions(SaveFormat.Html)
{
    ExportTextInputFormFieldAsText = true, 
    ImagesFolder = imagesDir
};

doc.Save(ArtifactsDir + "HtmlSaveOptions.SaveHtmlWithOptions.html", options);
```

### Voir également

* class [HtmlSaveOptions](../)
* espace de noms [Aspose.Words.Saving](../../htmlsaveoptions/)
* Assemblée [Aspose.Words](../../../)


