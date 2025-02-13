---
title: ImageSavingArgs.KeepImageStreamOpen
second_title: Référence de l'API Aspose.Words pour .NET
description: ImageSavingArgs propriété. Spécifie si Aspose.Words doit garder le flux ouvert ou le fermer après avoir enregistré une image.
type: docs
weight: 60
url: /fr/net/aspose.words.saving/imagesavingargs/keepimagestreamopen/
---
## ImageSavingArgs.KeepImageStreamOpen property

Spécifie si Aspose.Words doit garder le flux ouvert ou le fermer après avoir enregistré une image.

```csharp
public bool KeepImageStreamOpen { get; set; }
```

### Remarques

La valeur par défaut est`faux` et Aspose.Words fermera le flux que vous avez fourni dans le[`ImageStream`](../imagestream/) propriété après y avoir écrit une image. Spécifiez`vrai` pour garder le flux ouvert.

### Exemples

Montre comment impliquer un rappel d'enregistrement d'image dans un processus de conversion HTML.

```csharp
{
    Document doc = new Document(MyDir + "Rendering.docx");

    // Lorsque nous enregistrons le document au format HTML, nous pouvons passer un objet SaveOptions pour désigner un rappel
    // pour personnaliser le processus d'enregistrement de l'image.
    HtmlSaveOptions options = new HtmlSaveOptions();
    options.ImageSavingCallback = new ImageShapePrinter();

    doc.Save(ArtifactsDir + "HtmlSaveOptions.ImageSavingCallback.html", options);
}

/// <summary>
/// Imprime les propriétés de chaque image au fur et à mesure que le processus d'enregistrement l'enregistre dans un fichier image dans le système de fichiers local
/// lors de l'export d'un document en HTML.
/// </summary>
private class ImageShapePrinter : IImageSavingCallback
{
    void IImageSavingCallback.ImageSaving(ImageSavingArgs args)
    {
        args.KeepImageStreamOpen = false;
        Assert.True(args.IsImageAvailable);

        Console.WriteLine($"{args.Document.OriginalFileName.Split('\\').Last()} Image #{++mImageCount}");

        LayoutCollector layoutCollector = new LayoutCollector(args.Document);

        Console.WriteLine($"\tOn page:\t{layoutCollector.GetStartPageIndex(args.CurrentShape)}");
        Console.WriteLine($"\tDimensions:\t{args.CurrentShape.Bounds}");
        Console.WriteLine($"\tAlignment:\t{args.CurrentShape.VerticalAlignment}");
        Console.WriteLine($"\tWrap type:\t{args.CurrentShape.WrapType}");
        Console.WriteLine($"Output filename:\t{args.ImageFileName}\n");
    }

    private int mImageCount;
}
```

### Voir également

* class [ImageSavingArgs](../)
* espace de noms [Aspose.Words.Saving](../../imagesavingargs/)
* Assemblée [Aspose.Words](../../../)


