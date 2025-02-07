---
title: FixedPageSaveOptions.ColorMode
second_title: Référence de l'API Aspose.Words pour .NET
description: FixedPageSaveOptions propriété. Obtient ou définit une valeur déterminant le rendu des couleurs.
type: docs
weight: 10
url: /fr/net/aspose.words.saving/fixedpagesaveoptions/colormode/
---
## FixedPageSaveOptions.ColorMode property

Obtient ou définit une valeur déterminant le rendu des couleurs.

```csharp
public ColorMode ColorMode { get; set; }
```

### Remarques

La valeur par défaut estNormal .

### Exemples

Montre comment changer la couleur de l'image avec la propriété des options d'enregistrement.

```csharp
Document doc = new Document(MyDir + "Images.docx");

// Crée un objet "PdfSaveOptions" que nous pouvons passer à la méthode "Save" du document
// pour modifier la façon dont cette méthode convertit le document en .PDF.
// Définissez la propriété "ColorMode" sur "Grayscale" pour rendre toutes les images du document en noir et blanc.
// La taille du document de sortie peut être plus grande avec ce paramètre.
// Définissez la propriété "ColorMode" sur "Normal" pour rendre toutes les images en couleur.
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions { ColorMode = colorMode };

doc.Save(ArtifactsDir + "PdfSaveOptions.ColorRendering.pdf", pdfSaveOptions);
```

### Voir également

* enum [ColorMode](../../colormode/)
* class [FixedPageSaveOptions](../)
* espace de noms [Aspose.Words.Saving](../../fixedpagesaveoptions/)
* Assemblée [Aspose.Words](../../../)


