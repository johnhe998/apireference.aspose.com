---
title: PdfSaveOptions.DmlEffectsRenderingMode
second_title: Référence de l'API Aspose.Words pour .NET
description: PdfSaveOptions propriété. Obtient ou définit une valeur déterminant le rendu des effets DrawingML.
type: docs
weight: 80
url: /fr/net/aspose.words.saving/pdfsaveoptions/dmleffectsrenderingmode/
---
## PdfSaveOptions.DmlEffectsRenderingMode property

Obtient ou définit une valeur déterminant le rendu des effets DrawingML.

```csharp
public override DmlEffectsRenderingMode DmlEffectsRenderingMode { get; set; }
```

### Remarques

La valeur par défaut estSimplified .

Cette propriété est utilisée lorsque le document est exporté vers des formats de page fixes.

Si[`Compliance`](../compliance/) est réglé surPdfA1a ouPdfA1b , propriété renvoie toujoursNone.

### Exemples

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

* enum [DmlEffectsRenderingMode](../../dmleffectsrenderingmode/)
* class [PdfSaveOptions](../)
* espace de noms [Aspose.Words.Saving](../../pdfsaveoptions/)
* Assemblée [Aspose.Words](../../../)


