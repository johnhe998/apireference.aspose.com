---
title: ImageSaveOptions.TiffCompression
second_title: Référence de l'API Aspose.Words pour .NET
description: ImageSaveOptions propriété. Obtient ou définit le type de compression à appliquer lors de lenregistrement des images générées au format TIFF.
type: docs
weight: 170
url: /fr/net/aspose.words.saving/imagesaveoptions/tiffcompression/
---
## ImageSaveOptions.TiffCompression property

Obtient ou définit le type de compression à appliquer lors de l'enregistrement des images générées au format TIFF.

```csharp
public TiffCompression TiffCompression { get; set; }
```

### Remarques

N'a d'effet que lors de l'enregistrement au format TIFF.

La valeur par défaut estLzw.

### Exemples

Montre comment sélectionner le schéma de compression à appliquer à un document que nous convertissons en une image TIFF.

```csharp
Document doc = new Document();
            DocumentBuilder builder = new DocumentBuilder(doc);

            builder.InsertImage(ImageDir + "Logo.jpg");

            // Crée un objet "ImageSaveOptions" que nous pouvons passer à la méthode "Save" du document
            // pour modifier la façon dont cette méthode rend le document en image.
            ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Tiff);

            // Définissez la propriété "TiffCompression" sur "TiffCompression.None" pour n'appliquer aucune compression lors de l'enregistrement,
            // ce qui peut entraîner un fichier de sortie très volumineux.
            // Définissez la propriété "TiffCompression" sur "TiffCompression.Rle" pour appliquer la compression RLE
            // Définissez la propriété "TiffCompression" sur "TiffCompression.Lzw" pour appliquer la compression LZW.
            // Définissez la propriété "TiffCompression" sur "TiffCompression.Ccitt3" pour appliquer la compression CCITT3.
            // Définissez la propriété "TiffCompression" sur "TiffCompression.Ccitt4" pour appliquer la compression CCITT4.
            options.TiffCompression = tiffCompression;

            doc.Save(ArtifactsDir + "ImageSaveOptions.TiffImageCompression.tiff", options);

            switch (tiffCompression)
            {
                case TiffCompression.None:
                    Assert.That(3000000, Is.LessThan(new FileInfo(ArtifactsDir + "ImageSaveOptions.TiffImageCompression.tiff").Length));
                    break;
                case TiffCompression.Rle:
#if NET5_0_OR_GREATER
                    Assert.That(6000, Is.LessThan(new FileInfo(ArtifactsDir + "ImageSaveOptions.TiffImageCompression.tiff").Length));
#else
                    Assert.That(600000, Is.LessThan(new FileInfo(ArtifactsDir + "ImageSaveOptions.TiffImageCompression.tiff").Length));
#endif
                    break;
                case TiffCompression.Lzw:
                    Assert.That(200000, Is.LessThan(new FileInfo(ArtifactsDir + "ImageSaveOptions.TiffImageCompression.tiff").Length));
                    break;
                case TiffCompression.Ccitt3:
                    Assert.That(90000, Is.AtLeast(new FileInfo(ArtifactsDir + "ImageSaveOptions.TiffImageCompression.tiff").Length));
                    break;
                case TiffCompression.Ccitt4:
                    Assert.That(20000, Is.AtLeast(new FileInfo(ArtifactsDir + "ImageSaveOptions.TiffImageCompression.tiff").Length));
                    break;
            }
```

### Voir également

* enum [TiffCompression](../../tiffcompression/)
* class [ImageSaveOptions](../)
* espace de noms [Aspose.Words.Saving](../../imagesaveoptions/)
* Assemblée [Aspose.Words](../../../)


