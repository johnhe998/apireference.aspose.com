---
title: PdfSaveOptions.HeaderFooterBookmarksExportMode
second_title: Référence de l'API Aspose.Words pour .NET
description: PdfSaveOptions propriété. Détermine comment les signets dans les entêtes/pieds de page sont exportés.
type: docs
weight: 150
url: /fr/net/aspose.words.saving/pdfsaveoptions/headerfooterbookmarksexportmode/
---
## PdfSaveOptions.HeaderFooterBookmarksExportMode property

Détermine comment les signets dans les en-têtes/pieds de page sont exportés.

```csharp
public HeaderFooterBookmarksExportMode HeaderFooterBookmarksExportMode { get; set; }
```

### Remarques

La valeur par défaut estAll.

Cette propriété est utilisée conjointement avec la[`OutlineOptions`](../outlineoptions/) option.

### Exemples

Affiche le traitement des signets dans les en-têtes/pieds de page d'un document que nous rendons au format PDF.

```csharp
Document doc = new Document(MyDir + "Bookmarks in headers and footers.docx");

// Crée un objet "PdfSaveOptions" que nous pouvons passer à la méthode "Save" du document
// pour modifier la façon dont cette méthode convertit le document en .PDF.
PdfSaveOptions saveOptions = new PdfSaveOptions();

// Définissez la propriété "PageMode" sur "PdfPageMode.UseOutlines" pour afficher le volet de navigation du plan dans le PDF de sortie.
saveOptions.PageMode = PdfPageMode.UseOutlines;

// Définissez la propriété "DefaultBookmarksOutlineLevel" à "1" pour afficher tous
// signets au premier niveau du plan dans le PDF de sortie.
saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;

// Définissez la propriété "HeaderFooterBookmarksExportMode" sur "HeaderFooterBookmarksExportMode.None" pour
// n'exporte aucun signet qui se trouve dans les en-têtes/pieds de page.
// Définissez la propriété "HeaderFooterBookmarksExportMode" sur "HeaderFooterBookmarksExportMode.First" pour
// exporte uniquement les signets dans l'en-tête/le pied de page de la première section.
// Définissez la propriété "HeaderFooterBookmarksExportMode" sur "HeaderFooterBookmarksExportMode.All" pour
// exporte les signets qui se trouvent dans tous les en-têtes/pieds de page.
saveOptions.HeaderFooterBookmarksExportMode = headerFooterBookmarksExportMode;

doc.Save(ArtifactsDir + "PdfSaveOptions.HeaderFooterBookmarksExportMode.pdf", saveOptions);
```

### Voir également

* enum [HeaderFooterBookmarksExportMode](../../headerfooterbookmarksexportmode/)
* class [PdfSaveOptions](../)
* espace de noms [Aspose.Words.Saving](../../pdfsaveoptions/)
* Assemblée [Aspose.Words](../../../)


