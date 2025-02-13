---
title: ImageSaveOptions.TiffBinarizationMethod
second_title: Référence de l'API Aspose.Words pour .NET
description: ImageSaveOptions propriété. Obtient ou définit la méthode utilisée lors de la conversion des images au format 1 bpp lorsqueSaveFormat est SaveFormat.Tiff and TiffCompression est égal à TiffCompression.Ccitt3 ou TiffCompression.Ccitt4.
type: docs
weight: 160
url: /fr/net/aspose.words.saving/imagesaveoptions/tiffbinarizationmethod/
---
## ImageSaveOptions.TiffBinarizationMethod property

Obtient ou définit la méthode utilisée lors de la conversion des images au format 1 bpp lorsque[`SaveFormat`](../saveformat/) est SaveFormat.Tiff and [`TiffCompression`](../tiffcompression/) est égal à TiffCompression.Ccitt3 ou TiffCompression.Ccitt4.

```csharp
public ImageBinarizationMethod TiffBinarizationMethod { get; set; }
```

### Remarques

La valeur par défaut est ImageBinarizationMethod.Threshold.

### Exemples

Montre comment définir le seuil d'erreur de binarisation TIFF lors de l'utilisation de la méthode Floyd-Steinberg pour restituer une image TIFF.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ParagraphFormat.Style = doc.Styles["Heading 1"];
builder.Writeln("Hello world!");
builder.InsertImage(ImageDir + "Logo.jpg");

// Lorsque nous enregistrons le document au format TIFF, nous pouvons passer un objet SaveOptions à
// ajuste le tramage qu'Aspose.Words appliquera lors du rendu de cette image.
// La valeur par défaut de la propriété "ThresholdForFloydSteinbergDithering" est 128.
// Des valeurs plus élevées ont tendance à produire des images plus sombres.
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Tiff)
{
    TiffCompression = TiffCompression.Ccitt3,
    TiffBinarizationMethod = ImageBinarizationMethod.FloydSteinbergDithering,
    ThresholdForFloydSteinbergDithering = 240
};

doc.Save(ArtifactsDir + "ImageSaveOptions.FloydSteinbergDithering.tiff", options);
```

### Voir également

* enum [ImageBinarizationMethod](../../imagebinarizationmethod/)
* class [ImageSaveOptions](../)
* espace de noms [Aspose.Words.Saving](../../imagesaveoptions/)
* Assemblée [Aspose.Words](../../../)


