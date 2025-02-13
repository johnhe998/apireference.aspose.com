---
title: Enum DmlEffectsRenderingMode
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.Saving.DmlEffectsRenderingMode énumération. Spécifie comment les effets DrawingML sont rendus aux formats de page fixes.
type: docs
weight: 4650
url: /fr/net/aspose.words.saving/dmleffectsrenderingmode/
---
## DmlEffectsRenderingMode enumeration

Spécifie comment les effets DrawingML sont rendus aux formats de page fixes.

```csharp
public enum DmlEffectsRenderingMode
```

### Valeurs

| Nom | Évaluer | La description |
| --- | --- | --- |
| Simplified | `0` | Le rendu des effets DrawingML est simplifié. |
| None | `1` | Aucun effet DrawingML n'est rendu. |
| Fine | `2` | Les effets DrawingML sont rendus en mode fin qui implique un traitement avancé. Dans ce mode, le rendu des effets donne de meilleurs résultats mais à un coût de performance plus élevé queSimplified mode. |

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

* espace de noms [Aspose.Words.Saving](../../aspose.words.saving/)
* Assemblée [Aspose.Words](../../)


