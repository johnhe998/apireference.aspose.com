---
title: FileFormatUtil.ImageTypeToExtension
second_title: Référence de l'API Aspose.Words pour .NET
description: FileFormatUtil méthode. Convertit une valeur énumérée de type dimage Aspose.Words en une extension de fichier. Lextension renvoyée est une chaîne en minuscules précédée dun point.
type: docs
weight: 50
url: /fr/net/aspose.words/fileformatutil/imagetypetoextension/
---
## FileFormatUtil.ImageTypeToExtension method

Convertit une valeur énumérée de type d'image Aspose.Words en une extension de fichier. L'extension renvoyée est une chaîne en minuscules précédée d'un point.

```csharp
public static string ImageTypeToExtension(ImageType imageType)
```

### Exceptions

| exception | condition |
| --- | --- |
| ArgumentException | Lance lorsqu'il est impossible de convertir. |

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

* enum [ImageType](../../../aspose.words.drawing/imagetype/)
* class [FileFormatUtil](../)
* espace de noms [Aspose.Words](../../fileformatutil/)
* Assemblée [Aspose.Words](../../../)


