---
title: Class ThumbnailGeneratingOptions
second_title: Référence de l'API Aspose.Words pour .NET
description: Aspose.Words.Rendering.ThumbnailGeneratingOptions classe. Peut être utilisé pour spécifier des options supplémentaires lors de la génération dune vignette pour un document.
type: docs
weight: 4340
url: /fr/net/aspose.words.rendering/thumbnailgeneratingoptions/
---
## ThumbnailGeneratingOptions class

Peut être utilisé pour spécifier des options supplémentaires lors de la génération d'une vignette pour un document.

```csharp
public class ThumbnailGeneratingOptions
```

## Constructeurs

| Nom | La description |
| --- | --- |
| [ThumbnailGeneratingOptions](thumbnailgeneratingoptions/)() | Default_Constructor |

## Propriétés

| Nom | La description |
| --- | --- |
| [GenerateFromFirstPage](../../aspose.words.rendering/thumbnailgeneratingoptions/generatefromfirstpage/) { get; set; } | Spécifie s'il faut générer une vignette à partir de la première page du document ou de la première image. |
| [ThumbnailSize](../../aspose.words.rendering/thumbnailgeneratingoptions/thumbnailsize/) { get; set; } | Taille de la vignette générée en pixels. La valeur par défaut est 600x900. |

### Remarques

L'utilisateur peut appeler la méthode[`UpdateThumbnail`](../../aspose.words/document/updatethumbnail/) pour générer [`Thumbnail`](../../aspose.words.properties/builtindocumentproperties/thumbnail/) pour un document.

### Exemples

Montre comment mettre à jour la vignette d'un document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Hello world!");
builder.InsertImage(ImageDir + "Logo.jpg");

// Il existe deux manières de définir une image miniature lors de l'enregistrement d'un document au format .epub.
// 1 - Utiliser la première page du document :
doc.UpdateThumbnail();
doc.Save(ArtifactsDir + "Document.UpdateThumbnail.FirstPage.epub");

// 2 - Utiliser la première image trouvée dans le document :
ThumbnailGeneratingOptions options = new ThumbnailGeneratingOptions();
options.ThumbnailSize = new Size(400, 400);
options.GenerateFromFirstPage = false;

doc.UpdateThumbnail(options);
doc.Save(ArtifactsDir + "Document.UpdateThumbnail.FirstImage.epub");
```

### Voir également

* espace de noms [Aspose.Words.Rendering](../../aspose.words.rendering/)
* Assemblée [Aspose.Words](../../)


