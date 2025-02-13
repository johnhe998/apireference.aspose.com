---
title: PdfSaveOptions.Compliance
second_title: Référence de l'API Aspose.Words pour .NET
description: PdfSaveOptions propriété. Spécifie le niveau de conformité aux normes PDF pour les documents de sortie.
type: docs
weight: 30
url: /fr/net/aspose.words.saving/pdfsaveoptions/compliance/
---
## PdfSaveOptions.Compliance property

Spécifie le niveau de conformité aux normes PDF pour les documents de sortie.

```csharp
public PdfCompliance Compliance { get; set; }
```

### Remarques

La valeur par défaut estPdf17.

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

* enum [PdfCompliance](../../pdfcompliance/)
* class [PdfSaveOptions](../)
* espace de noms [Aspose.Words.Saving](../../pdfsaveoptions/)
* Assemblée [Aspose.Words](../../../)


