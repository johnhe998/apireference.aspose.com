---
title: PdfSaveOptions.ZoomBehavior
second_title: Référence de l'API Aspose.Words pour .NET
description: PdfSaveOptions propriété. Obtient ou définit une valeur déterminant le type de zoom à appliquer lorsquun document est ouvert avec une visionneuse PDF.
type: docs
weight: 290
url: /fr/net/aspose.words.saving/pdfsaveoptions/zoombehavior/
---
## PdfSaveOptions.ZoomBehavior property

Obtient ou définit une valeur déterminant le type de zoom à appliquer lorsqu'un document est ouvert avec une visionneuse PDF.

```csharp
public PdfZoomBehavior ZoomBehavior { get; set; }
```

### Remarques

La valeur par défaut estNone , c'est-à-dire qu'aucun ajustement n'est appliqué.

### Exemples

Montre comment définir le zoom par défaut qu'un lecteur applique lors de l'ouverture d'un document PDF rendu.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

// Crée un objet "PdfSaveOptions" que nous pouvons passer à la méthode "Save" du document
// pour modifier la façon dont cette méthode convertit le document en .PDF.
// Définissez la propriété "ZoomBehavior" sur "PdfZoomBehavior.ZoomFactor" pour obtenir un lecteur PDF
// applique un facteur de zoom basé sur un pourcentage lorsque nous ouvrons le document avec.
// Définissez la propriété "ZoomFactor" sur "25" pour donner au facteur de zoom une valeur de 25 %.
PdfSaveOptions options = new PdfSaveOptions
{
    ZoomBehavior = PdfZoomBehavior.ZoomFactor,
    ZoomFactor = 25
};

// Lorsque nous ouvrons ce document à l'aide d'un lecteur tel qu'Adobe Acrobat, nous verrons le document mis à l'échelle à 1/4 de sa taille réelle.
doc.Save(ArtifactsDir + "PdfSaveOptions.ZoomBehaviour.pdf", options);
```

### Voir également

* enum [PdfZoomBehavior](../../pdfzoombehavior/)
* class [PdfSaveOptions](../)
* espace de noms [Aspose.Words.Saving](../../pdfsaveoptions/)
* Assemblée [Aspose.Words](../../../)


