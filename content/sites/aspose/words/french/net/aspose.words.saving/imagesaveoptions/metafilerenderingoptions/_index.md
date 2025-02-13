---
title: ImageSaveOptions.MetafileRenderingOptions
second_title: Référence de l'API Aspose.Words pour .NET
description: ImageSaveOptions propriété. Permet de spécifier comment les métafichiers sont traités dans la sortie rendue.
type: docs
weight: 80
url: /fr/net/aspose.words.saving/imagesaveoptions/metafilerenderingoptions/
---
## ImageSaveOptions.MetafileRenderingOptions property

Permet de spécifier comment les métafichiers sont traités dans la sortie rendue.

```csharp
public MetafileRenderingOptions MetafileRenderingOptions { get; }
```

### Remarques

LorsqueVector est spécifié, Aspose.Words rend le métafichier aux graphiques vectoriels en utilisant d'abord son propre moteur de rendu de métafichier, puis restitue les graphiques vector à l'image.

LorsqueBitmap est spécifié, Aspose.Words rend le métafichier directement dans l'image à l'aide du moteur de rendu du métafichier GDI+.

Le moteur de rendu de métafichier GDI+ fonctionne plus rapidement, prend en charge presque toutes les fonctionnalités de métafichier, mais les résolutions low peuvent produire des résultats incohérents par rapport au reste des graphiques vectoriels (en particulier pour le texte) sur la page. Le moteur de rendu du métafichier Aspose.Words produit un résultat plus cohérent even sur les basses résolutions, mais fonctionne plus lentement et peut restituer de manière inexacte les métafichiers complexes.

La valeur par défaut pour[`MetafileRenderingMode`](../../metafilerenderingmode/) estBitmap.

### Exemples

Montre comment définir le mode de rendu lors de l'enregistrement de documents avec des images de métafichier Windows dans d'autres formats d'image.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertImage(Image.FromFile(ImageDir + "Windows MetaFile.wmf"));

// Lorsque nous enregistrons le document en tant qu'image, nous pouvons passer un objet SaveOptions à
// détermine comment l'opération d'enregistrement traitera les métafichiers Windows dans le document.
// Si nous définissons la propriété "RenderingMode" sur "MetafileRenderingMode.Vector",
// ou "MetafileRenderingMode.VectorWithFallback", nous afficherons tous les métafichiers sous forme de graphiques vectoriels.
// Si nous définissons la propriété "RenderingMode" sur "MetafileRenderingMode.Bitmap", nous afficherons tous les métafichiers sous forme de bitmaps.
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Png);
options.MetafileRenderingOptions.RenderingMode = metafileRenderingMode;

doc.Save(ArtifactsDir + "ImageSaveOptions.WindowsMetaFile.png", options);
```

### Voir également

* class [MetafileRenderingOptions](../../metafilerenderingoptions/)
* class [ImageSaveOptions](../)
* espace de noms [Aspose.Words.Saving](../../imagesaveoptions/)
* Assemblée [Aspose.Words](../../../)


