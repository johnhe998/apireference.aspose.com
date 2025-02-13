---
title: MarkdownSaveOptions.ImagesFolder
second_title: Référence de l'API Aspose.Words pour .NET
description: MarkdownSaveOptions propriété. Spécifie le dossier physique dans lequel les images sont enregistrées lors de lexportation dun document vers leMarkdown format. La valeur par défaut est une chaîne vide.
type: docs
weight: 40
url: /fr/net/aspose.words.saving/markdownsaveoptions/imagesfolder/
---
## MarkdownSaveOptions.ImagesFolder property

Spécifie le dossier physique dans lequel les images sont enregistrées lors de l'exportation d'un document vers leMarkdown format. La valeur par défaut est une chaîne vide.

```csharp
public string ImagesFolder { get; set; }
```

### Remarques

Lorsque vous enregistrez un[`Document`](../../../aspose.words/document/) dansMarkdown format, Aspose.Words doit enregistrer toutes les images intégrées dans le document en tant que fichiers autonomes. `ImagesFolder` vous permet de spécifier où les images seront enregistrées.

Si vous enregistrez un document dans un fichier et fournissez un nom de fichier, Aspose.Words, par défaut, enregistre les images dans le même dossier où le fichier du document est enregistré. Utilisation`ImagesFolder` pour remplacer ce comportement.

Si vous enregistrez un document dans un flux, Aspose.Words n'a pas de dossier où enregistrer les images, mais doit toujours enregistrer les images quelque part. Dans ce cas, vous devez spécifier un dossier accessible dans le`ImagesFolder` propriété.

Si le dossier spécifié par`ImagesFolder` n'existe pas, il sera créé automatiquement.

### Voir également

* class [MarkdownSaveOptions](../)
* espace de noms [Aspose.Words.Saving](../../markdownsaveoptions/)
* Assemblée [Aspose.Words](../../../)


