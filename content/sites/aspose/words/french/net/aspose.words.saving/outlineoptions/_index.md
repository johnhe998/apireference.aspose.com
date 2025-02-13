---
title: Class OutlineOptions
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.Saving.OutlineOptions classe. Permet de spécifier les options de contour.
type: docs
weight: 5080
url: /fr/net/aspose.words.saving/outlineoptions/
---
## OutlineOptions class

Permet de spécifier les options de contour.

```csharp
public class OutlineOptions
```

## Constructeurs

| Nom | La description |
| --- | --- |
| [OutlineOptions](outlineoptions/)() | Default_Constructor |

## Propriétés

| Nom | La description |
| --- | --- |
| [BookmarksOutlineLevels](../../aspose.words.saving/outlineoptions/bookmarksoutlinelevels/) { get; } | Permet de spécifier le niveau de contour des signets individuels. |
| [CreateMissingOutlineLevels](../../aspose.words.saving/outlineoptions/createmissingoutlinelevels/) { get; set; } | Obtient ou définit une valeur déterminant s'il faut ou non créer des niveaux hiérarchiques manquants lorsque le document est exporté. |
| [CreateOutlinesForHeadingsInTables](../../aspose.words.saving/outlineoptions/createoutlinesforheadingsintables/) { get; set; } | Spécifie s'il faut ou non créer des contours pour les en-têtes (paragraphes formatés avec les styles d'en-tête) à l'intérieur des tableaux. |
| [DefaultBookmarksOutlineLevel](../../aspose.words.saving/outlineoptions/defaultbookmarksoutlinelevel/) { get; set; } | Spécifie le niveau par défaut dans le plan du document auquel afficher les signets Word. |
| [ExpandedOutlineLevels](../../aspose.words.saving/outlineoptions/expandedoutlinelevels/) { get; set; } | Spécifie le nombre de niveaux dans le plan du document à afficher développés lorsque le fichier est affiché. |
| [HeadingsOutlineLevels](../../aspose.words.saving/outlineoptions/headingsoutlinelevels/) { get; set; } | Spécifie le nombre de niveaux de titres (paragraphes formatés avec les styles de titre) à inclure dans le plan du document . |

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

* espace de noms [Aspose.Words.Saving](../../aspose.words.saving/)
* Assemblée [Aspose.Words](../../)


