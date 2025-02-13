---
title: Enum PdfCompliance
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.Saving.PdfCompliance énumération. Spécifie le niveau de conformité aux normes PDF.
type: docs
weight: 5130
url: /fr/net/aspose.words.saving/pdfcompliance/
---
## PdfCompliance enumeration

Spécifie le niveau de conformité aux normes PDF.

```csharp
public enum PdfCompliance
```

### Valeurs

| Nom | Évaluer | La description |
| --- | --- | --- |
| Pdf17 | `0` | Le fichier de sortie sera conforme à la norme PDF 1.7 (ISO 32000-1). |
| Pdf20 | `1` | Le fichier de sortie sera conforme à la norme PDF 2.0 (ISO 32000-2). |
| PdfA1a | `2` | Le fichier de sortie sera conforme à la norme PDF/A-1a (ISO 19005-1). Ce niveau comprend toutes les exigences de PDF/A-1b et nécessite en outre que la structure du document soit incluse (également connue sous le nom de "balisé" ), dans le but de garantir que le contenu du document peut être recherché et réutilisé. |
| PdfA1b | `3` | Le fichier de sortie sera conforme à la norme PDF/A-1b (ISO 19005-1). PDF/A-1b a pour objectif d'assurer une reproduction fiable de l' aspect visuel du document. |
| PdfA2a | `4` | Le fichier de sortie sera conforme à la norme PDF/A-2a (ISO 19005-2). Ce niveau comprend toutes les exigences de PDF/A-2u et nécessite en outre que la structure du document soit incluse (également connue sous le nom de "balisé" ), dans le but de garantir que le contenu du document peut être recherché et réutilisé. |
| PdfA2u | `5` | Le fichier de sortie sera conforme à la norme PDF/A-2u (ISO 19005-2). PDF/A-2u a pour objectif de préserver l'aspect visuel statique du document dans le temps, indépendamment des outils et des systèmes utilisés pour créer, stocker ou rendre les fichiers. De plus, tout texte contenu dans le document peut être extrait de manière fiable sous la forme d'une série de points de code Unicode. |
| PdfA4 | `6` | Le fichier de sortie sera conforme à la norme PDF/A-4 (ISO 19005-4:2020). PDF/A-4 a pour objectif de préserver l'aspect visuel statique du document dans le temps, indépendamment des outils et des systèmes utilisés pour créer , stocker ou restituer les fichiers. De plus, tout texte contenu dans le document peut être extrait de manière fiable sous la forme d'une série de points de code Unicode. |
| PdfUa1 | `7` | Le fichier de sortie sera conforme à la norme PDF/UA-1 (ISO 14289-1). L'objectif principal de PDF/UA est de définir comment représenter les documents électroniques au format PDF d'une manière qui permet au fichier d'être accessibles. |

### Exemples

Montre comment définir le niveau de conformité aux normes PDF des documents PDF enregistrés.

```csharp
Document doc = new Document(MyDir + "Images.docx");

// Crée un objet "PdfSaveOptions" que nous pouvons passer à la méthode "Save" du document
// pour modifier la façon dont cette méthode convertit le document en .PDF.
// Notez que certaines PdfSaveOptions sont interdites lors de l'enregistrement dans l'une des normes et automatiquement corrigées.
// Utilisez IWarningCallback pour savoir quelles options sont automatiquement corrigées.
PdfSaveOptions saveOptions = new PdfSaveOptions();

// Définissez la propriété "Compliance" à "PdfCompliance.PdfA1b" pour respecter la norme "PDF/A-1b",
// qui vise à préserver l'apparence visuelle du document au fur et à mesure qu'Aspose.Words le convertit en PDF.
// Définissez la propriété "Compliance" sur "PdfCompliance.Pdf17" pour respecter la norme "1.7".
// Définissez la propriété "Compliance" sur "PdfCompliance.PdfA1a" pour respecter la norme "PDF/A-1a",
// qui est conforme à "PDF/A-1b" tout en préservant la structure du document d'origine.
// Définissez la propriété "Compliance" sur "PdfCompliance.PdfUa1" pour respecter la norme "PDF/UA-1" (ISO 14289-1),
// qui vise à définir représenter des documents électroniques en PDF permettant au fichier d'être accessible.
// Cela aide à rendre les documents consultables, mais peut augmenter considérablement la taille de documents déjà volumineux.
saveOptions.Compliance = pdfCompliance;

doc.Save(ArtifactsDir + "PdfSaveOptions.Compliance.pdf", saveOptions);
```

### Voir également

* espace de noms [Aspose.Words.Saving](../../aspose.words.saving/)
* Assemblée [Aspose.Words](../../)


