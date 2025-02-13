---
title: Enum EmfPlusDualRenderingMode
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.Saving.EmfPlusDualRenderingMode énumération. Spécifie comment Aspose.Words doit restituer les métafichiers EMF Dual.
type: docs
weight: 4720
url: /fr/net/aspose.words.saving/emfplusdualrenderingmode/
---
## EmfPlusDualRenderingMode enumeration

Spécifie comment Aspose.Words doit restituer les métafichiers EMF+ Dual.

```csharp
public enum EmfPlusDualRenderingMode
```

### Valeurs

| Nom | Évaluer | La description |
| --- | --- | --- |
| EmfPlusWithFallback | `0` | Aspose.Words essaie de restituer la partie EMF+ du métafichier EMF+ Dual. Si certains des enregistrements EMF+ ne sont pas pris en charge , alors Aspose.Words rend la partie EMF du métafichier EMF+ Dual. |
| EmfPlus | `1` | Aspose.Words rend la partie EMF+ du métafichier EMF+ Dual. |
| Emf | `2` | Aspose.Words rend la partie EMF du métafichier EMF+ Dual. |

### Exemples

Montre comment configurer les options de rendu liées au métafichier Windows amélioré lors de l'enregistrement au format PDF.

```csharp
Document doc = new Document(MyDir + "EMF.docx");

// Crée un objet "PdfSaveOptions" que nous pouvons passer à la méthode "Save" du document
// pour modifier la façon dont cette méthode convertit le document en .PDF.
PdfSaveOptions saveOptions = new PdfSaveOptions();

// Définissez la propriété "EmfPlusDualRenderingMode" sur "EmfPlusDualRenderingMode.Emf"
// pour afficher uniquement la partie EMF d'un métafichier double EMF+.
// Définissez la propriété "EmfPlusDualRenderingMode" sur "EmfPlusDualRenderingMode.EmfPlus" pour
// pour restituer la partie EMF+ d'un métafichier double EMF+.
// Définissez la propriété "EmfPlusDualRenderingMode" sur "EmfPlusDualRenderingMode.EmfPlusWithFallback"
// pour restituer la partie EMF+ d'un double métafichier EMF+ si tous les enregistrements EMF+ sont pris en charge.
// Sinon, Aspose.Words rendra la partie EMF.
saveOptions.MetafileRenderingOptions.EmfPlusDualRenderingMode = renderingMode;

// Définissez la propriété "UseEmfEmbeddedToWmf" sur "true" pour restituer les données EMF intégrées
// pour les métafichiers que nous pouvons afficher sous forme de graphiques vectoriels.
saveOptions.MetafileRenderingOptions.UseEmfEmbeddedToWmf = true;

doc.Save(ArtifactsDir + "PdfSaveOptions.RenderMetafile.pdf", saveOptions);
```

### Voir également

* espace de noms [Aspose.Words.Saving](../../aspose.words.saving/)
* Assemblée [Aspose.Words](../../)


