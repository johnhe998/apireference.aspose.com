---
title: SaveOptions.DmlRenderingMode
second_title: Référence de l'API Aspose.Words pour .NET
description: SaveOptions propriété. Obtient ou définit une valeur déterminant le rendu des formes DrawingML.
type: docs
weight: 70
url: /fr/net/aspose.words.saving/saveoptions/dmlrenderingmode/
---
## SaveOptions.DmlRenderingMode property

Obtient ou définit une valeur déterminant le rendu des formes DrawingML.

```csharp
public DmlRenderingMode DmlRenderingMode { get; set; }
```

### Remarques

La valeur par défaut estFallback .

Cette propriété est utilisée lorsque le document est exporté vers des formats de page fixes.

### Exemples

Montre comment rendre les formes de secours lors de l'enregistrement au format PDF.

```csharp
Document doc = new Document(MyDir + "DrawingML shape fallbacks.docx");

// Crée un objet "PdfSaveOptions" que nous pouvons passer à la méthode "Save" du document
// pour modifier la façon dont cette méthode convertit le document en .PDF.
PdfSaveOptions options = new PdfSaveOptions();

// Définissez la propriété "DmlRenderingMode" sur "DmlRenderingMode.Fallback"
// pour remplacer les formes DML par leurs formes de secours.
// Définissez la propriété "DmlRenderingMode" sur "DmlRenderingMode.DrawingML"
// pour restituer les formes DML elles-mêmes.
options.DmlRenderingMode = dmlRenderingMode;

doc.Save(ArtifactsDir + "PdfSaveOptions.DrawingMLFallback.pdf", options);
```

Montre comment configurer la qualité de rendu des effets DrawingML dans un document lorsque nous l'enregistrons au format PDF.

```csharp
Document doc = new Document(MyDir + "DrawingML shape effects.docx");

// Crée un objet "PdfSaveOptions" que nous pouvons passer à la méthode "Save" du document
// pour modifier la façon dont cette méthode convertit le document en .PDF.
PdfSaveOptions options = new PdfSaveOptions();

// Définissez la propriété "DmlEffectsRenderingMode" sur "DmlEffectsRenderingMode.None" pour supprimer tous les effets DrawingML.
// Définissez la propriété "DmlEffectsRenderingMode" sur "DmlEffectsRenderingMode.Simplified"
// pour rendre une version simplifiée des effets DrawingML.
// Définissez la propriété "DmlEffectsRenderingMode" sur "DmlEffectsRenderingMode.Fine" pour
// Rendre les effets DrawingML avec plus de précision et aussi avec plus de coût de traitement.
options.DmlEffectsRenderingMode = effectsRenderingMode;

Assert.AreEqual(DmlRenderingMode.DrawingML, options.DmlRenderingMode);

doc.Save(ArtifactsDir + "PdfSaveOptions.DrawingMLEffects.pdf", options);
```

### Voir également

* enum [DmlRenderingMode](../../dmlrenderingmode/)
* class [SaveOptions](../)
* espace de noms [Aspose.Words.Saving](../../saveoptions/)
* Assemblée [Aspose.Words](../../../)


