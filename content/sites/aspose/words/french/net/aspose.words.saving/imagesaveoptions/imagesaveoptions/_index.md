---
title: ImageSaveOptions.ImageSaveOptions
second_title: Référence de l'API Aspose.Words pour .NET
description: ImageSaveOptions constructeur. Initialise une nouvelle instance de cette classe qui peut être utilisée pour enregistrer les images rendues dans the Tiff Png Bmp  Emf Jpeg ouSvg format. Png Bmp Jpeg ouSvg format.
type: docs
weight: 10
url: /fr/net/aspose.words.saving/imagesaveoptions/imagesaveoptions/
---
## ImageSaveOptions constructor

Initialise une nouvelle instance de cette classe qui peut être utilisée pour enregistrer les images rendues dans the Tiff ,Png ,Bmp , Emf ,Jpeg ouSvg format. Png ,Bmp ,Jpeg ouSvg format.

```csharp
public ImageSaveOptions(SaveFormat saveFormat)
```

| Paramètre | Taper | La description |
| --- | --- | --- |
| saveFormat | SaveFormat | Peut être Tiff ,Png ,Bmp , Emf ,Jpeg ouSvg . Png ,Bmp ,Jpeg ouSvg . |

### Exemples

Montre comment configurer la compression lors de l'enregistrement d'un document au format JPEG.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertImage(ImageDir + "Logo.jpg");

// Crée un objet "ImageSaveOptions" que nous pouvons passer à la méthode "Save" du document
// pour modifier la façon dont cette méthode rend le document en image.
ImageSaveOptions imageOptions = new ImageSaveOptions(SaveFormat.Jpeg);

// Définissez la propriété "JpegQuality" sur "10" pour utiliser une compression plus forte lors du rendu du document.
// Cela réduira la taille du fichier du document, mais l'image affichera des artefacts de compression plus importants.
imageOptions.JpegQuality = 10;

doc.Save(ArtifactsDir + "ImageSaveOptions.JpegQuality.HighCompression.jpg", imageOptions);

Assert.That(20000, Is.AtLeast(new FileInfo(ArtifactsDir + "ImageSaveOptions.JpegQuality.HighCompression.jpg").Length));

// Définissez la propriété "JpegQuality" sur "100" pour utiliser une compression plus faible lors du rendu du document.
// Cela améliorera la qualité de l'image au prix d'une taille de fichier accrue.
imageOptions.JpegQuality = 100;

doc.Save(ArtifactsDir + "ImageSaveOptions.JpegQuality.HighQuality.jpg", imageOptions);

Assert.That(60000, Is.LessThan(new FileInfo(ArtifactsDir + "ImageSaveOptions.JpegQuality.HighQuality.jpg").Length));
```

### Voir également

* enum [SaveFormat](../../../aspose.words/saveformat/)
* class [ImageSaveOptions](../)
* espace de noms [Aspose.Words.Saving](../../imagesaveoptions/)
* Assemblée [Aspose.Words](../../../)


