---
title: Class DownsampleOptions
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.Saving.DownsampleOptions classe. Permet de spécifier les options de souséchantillonnage.
type: docs
weight: 4710
url: /fr/net/aspose.words.saving/downsampleoptions/
---
## DownsampleOptions class

Permet de spécifier les options de sous-échantillonnage.

```csharp
public class DownsampleOptions
```

## Constructeurs

| Nom | La description |
| --- | --- |
| [DownsampleOptions](downsampleoptions/)() | Default_Constructor |

## Propriétés

| Nom | La description |
| --- | --- |
| [DownsampleImages](../../aspose.words.saving/downsampleoptions/downsampleimages/) { get; set; } | Spécifie si les images doivent être sous-échantillonnées. |
| [Resolution](../../aspose.words.saving/downsampleoptions/resolution/) { get; set; } | Spécifie la résolution en pixels par pouce à laquelle les images doivent être sous-échantillonnées. |
| [ResolutionThreshold](../../aspose.words.saving/downsampleoptions/resolutionthreshold/) { get; set; } | Spécifie la résolution de seuil en pixels par pouce. Si la résolution d'une image dans le document est inférieure à la valeur de seuil, l'algorithme de sous-échantillonnage ne sera pas appliqué. Une valeur de 0 signifie que la vérification de seuil n'est pas utilisée et que toutes les images qui peuvent être réduits en taille sont sous-échantillonnés. |

### Exemples

Montre comment modifier la résolution des images dans le document PDF.

```csharp
Document doc = new Document(MyDir + "Images.docx");

// Crée un objet "PdfSaveOptions" que nous pouvons passer à la méthode "Save" du document
// pour modifier la façon dont cette méthode convertit le document en .PDF.
PdfSaveOptions options = new PdfSaveOptions();

// Par défaut, Aspose.Words sous-échantillonne toutes les images d'un document que nous enregistrons au format PDF à 220 ppi.
Assert.True(options.DownsampleOptions.DownsampleImages);
Assert.AreEqual(220, options.DownsampleOptions.Resolution);
Assert.AreEqual(0, options.DownsampleOptions.ResolutionThreshold);

doc.Save(ArtifactsDir + "PdfSaveOptions.DownsampleOptions.Default.pdf", options);

// Définissez la propriété "Résolution" sur "36" pour sous-échantillonner toutes les images à 36 ppi.
options.DownsampleOptions.Resolution = 36;

// Définissez la propriété "ResolutionThreshold" pour n'appliquer le sous-échantillonnage qu'à
// images avec une résolution supérieure à 128 ppi.
options.DownsampleOptions.ResolutionThreshold = 128;

// Seules les deux premières images du document seront sous-échantillonnées à ce stade.
doc.Save(ArtifactsDir + "PdfSaveOptions.DownsampleOptions.LowerResolution.pdf", options);
```

### Voir également

* espace de noms [Aspose.Words.Saving](../../aspose.words.saving/)
* Assemblée [Aspose.Words](../../)


