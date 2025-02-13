---
title: Document.UpdateThumbnail
second_title: Référence de l'API Aspose.Words pour .NET
description: Document méthode. Mises à jourThumbnail du document selon les options spécifiées.
type: docs
weight: 760
url: /fr/net/aspose.words/document/updatethumbnail/
---
## UpdateThumbnail(ThumbnailGeneratingOptions) {#updatethumbnail_1}

Mises à jour[`Thumbnail`](../../../aspose.words.properties/builtindocumentproperties/thumbnail/) du document selon les options spécifiées.

```csharp
public void UpdateThumbnail(ThumbnailGeneratingOptions options)
```

| Paramètre | Taper | La description |
| --- | --- | --- |
| options | ThumbnailGeneratingOptions | Les options de génération à utiliser. |

### Remarques

Le[`ThumbnailGeneratingOptions`](../../../aspose.words.rendering/thumbnailgeneratingoptions/) vous permet de spécifier la source de la vignette, sa taille et d'autres options. Si la tentative de génération de la vignette échoue, n'en change pas une.

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

* class [ThumbnailGeneratingOptions](../../../aspose.words.rendering/thumbnailgeneratingoptions/)
* class [Document](../)
* espace de noms [Aspose.Words](../../document/)
* Assemblée [Aspose.Words](../../../)

---

## UpdateThumbnail() {#updatethumbnail}

Mises à jour[`Thumbnail`](../../../aspose.words.properties/builtindocumentproperties/thumbnail/) du document en utilisant les options par défaut.

```csharp
public void UpdateThumbnail()
```

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

* class [Document](../)
* espace de noms [Aspose.Words](../../document/)
* Assemblée [Aspose.Words](../../../)


