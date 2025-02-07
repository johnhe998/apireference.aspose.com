---
title: ImageData.Save
second_title: Référence de l'API Aspose.Words pour .NET
description: ImageData méthode. Enregistre limage dans le flux spécifié.
type: docs
weight: 190
url: /fr/net/aspose.words.drawing/imagedata/save/
---
## Save(Stream) {#save}

Enregistre l'image dans le flux spécifié.

```csharp
public void Save(Stream stream)
```

| Paramètre | Taper | La description |
| --- | --- | --- |
| stream | Stream | Le flux dans lequel enregistrer l'image. |

### Remarques

Est-ce la responsabilité de l'appelant de disposer de l'objet flux.

### Exemples

Montre comment enregistrer toutes les images d'un document dans le système de fichiers.

```csharp
Document imgSourceDoc = new Document(MyDir + "Images.docx");

// Les formes avec le drapeau "HasImage" défini stockent et affichent toutes les images du document.
IEnumerable<Shape> shapesWithImages = 
    imgSourceDoc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Where(s => s.HasImage);

// Parcourez chaque forme et enregistrez son image.
ImageFormatConverter formatConverter = new ImageFormatConverter();

using (IEnumerator<Shape> enumerator = shapesWithImages.GetEnumerator())
{
    int shapeIndex = 0;

    while (enumerator.MoveNext())
    {
        ImageData imageData = enumerator.Current.ImageData;
        ImageFormat format = imageData.ToImage().RawFormat;
        string fileExtension = formatConverter.ConvertToString(format);

        using (FileStream fileStream = File.Create(ArtifactsDir + $"Drawing.SaveAllImages.{++shapeIndex}.{fileExtension}"))
            imageData.Save(fileStream);
    }
}
```

### Voir également

* class [ImageData](../)
* espace de noms [Aspose.Words.Drawing](../../imagedata/)
* Assemblée [Aspose.Words](../../../)

---

## Save(string) {#save_1}

Enregistre l'image dans un fichier.

```csharp
public void Save(string fileName)
```

| Paramètre | Taper | La description |
| --- | --- | --- |
| fileName | String | Le nom du fichier où enregistrer l'image. |

### Exemples

Montre comment extraire des images d'un document et les enregistrer dans le système de fichiers local en tant que fichiers individuels.

```csharp
Document doc = new Document(MyDir + "Images.docx");

// Récupère la collection de formes du document,
// et enregistrez les données d'image de chaque forme avec une image en tant que fichier dans le système de fichiers local.
NodeCollection shapes = doc.GetChildNodes(NodeType.Shape, true);

Assert.AreEqual(9, shapes.Count(s => ((Shape)s).HasImage));

int imageIndex = 0;
foreach (Shape shape in shapes.OfType<Shape>())
{
    if (shape.HasImage)
    {
        // Les données d'image des formes peuvent contenir des images de nombreux formats d'image possibles. 
        // Nous pouvons déterminer automatiquement une extension de fichier pour chaque image, en fonction de son format.
        string imageFileName =
            $"File.ExtractImages.{imageIndex}{FileFormatUtil.ImageTypeToExtension(shape.ImageData.ImageType)}";
        shape.ImageData.Save(ArtifactsDir + imageFileName);
        imageIndex++;
    }
}
```

### Voir également

* class [ImageData](../)
* espace de noms [Aspose.Words.Drawing](../../imagedata/)
* Assemblée [Aspose.Words](../../../)


