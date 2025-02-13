---
title: PdfSaveOptions.UseBookFoldPrintingSettings
second_title: Référence de l'API Aspose.Words pour .NET
description: PdfSaveOptions propriété. Obtient ou définit une valeur booléenne indiquant si le document doit être enregistré en utilisant une mise en page dimpression de livret si elle est spécifiée viaMultiplePages .
type: docs
weight: 270
url: /fr/net/aspose.words.saving/pdfsaveoptions/usebookfoldprintingsettings/
---
## PdfSaveOptions.UseBookFoldPrintingSettings property

Obtient ou définit une valeur booléenne indiquant si le document doit être enregistré en utilisant une mise en page d'impression de livret, si elle est spécifiée via[`MultiplePages`](../../../aspose.words/pagesetup/multiplepages/) .

```csharp
public bool UseBookFoldPrintingSettings { get; set; }
```

### Remarques

Si cette option est spécifiée,[`PageSet`](../../fixedpagesaveoptions/pageset/) est ignoré lors de l'enregistrement. Ce comportement correspond à MS Word. Si les paramètres d'impression de pliage de livre ne sont pas spécifiés dans la mise en page, cette option n'aura aucun effet.

### Exemples

Montre comment enregistrer un document au format PDF sous la forme d'un pli de livre.

```csharp
Document doc = new Document(MyDir + "Paragraphs.docx");

// Crée un objet "PdfSaveOptions" que nous pouvons passer à la méthode "Save" du document
// pour modifier la façon dont cette méthode convertit le document en .PDF.
PdfSaveOptions options = new PdfSaveOptions();

// Définissez la propriété "UseBookFoldPrintingSettings" sur "true" pour organiser le contenu
// dans le PDF de sortie d'une manière qui nous aide à l'utiliser pour créer un livret.
// Définissez la propriété "UseBookFoldPrintingSettings" sur "false" pour restituer le PDF normalement.
options.UseBookFoldPrintingSettings = renderTextAsBookfold;

// Si nous rendons le document sous forme de livret, nous devons définir le "MultiplePages"
// propriétés des objets de mise en page de toutes les sections à "MultiplePagesType.BookFoldPrinting".
if (renderTextAsBookfold)
    foreach (Section s in doc.Sections)
    {
        s.PageSetup.MultiplePages = MultiplePagesType.BookFoldPrinting;
    }

// Une fois que nous imprimons ce document des deux côtés des pages, nous pouvons plier toutes les pages au milieu à la fois,
// et le contenu s'alignera de manière à créer un livret.
doc.Save(ArtifactsDir + "PdfSaveOptions.SaveAsPdfBookFold.pdf", options);
```

### Voir également

* class [PdfSaveOptions](../)
* espace de noms [Aspose.Words.Saving](../../pdfsaveoptions/)
* Assemblée [Aspose.Words](../../../)


