---
title: Shape.ImageData
second_title: Référence de l'API Aspose.Words pour .NET
description: Shape propriété. Fournit un accès à limage de la forme. Renvoie null si la forme ne peut pas avoir dimage.
type: docs
weight: 110
url: /fr/net/aspose.words.drawing/shape/imagedata/
---
## Shape.ImageData property

Fournit un accès à l'image de la forme. Renvoie null si la forme ne peut pas avoir d'image.

```csharp
public ImageData ImageData { get; }
```

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

Montre comment insérer une image liée dans un document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

string imageFileName = ImageDir + "Windows MetaFile.wmf";

// Vous trouverez ci-dessous deux manières d'appliquer une image à une forme afin qu'elle puisse l'afficher.
// 1 - Définir la forme pour contenir l'image.
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape.WrapType = WrapType.Inline;
shape.ImageData.SetImage(imageFileName);

builder.InsertNode(shape);

doc.Save(ArtifactsDir + "Image.CreateLinkedImage.Embedded.docx");

// Chaque image que nous stockons dans shape augmentera la taille de notre document.
Assert.True(70000 < new FileInfo(ArtifactsDir + "Image.CreateLinkedImage.Embedded.docx").Length);

doc.FirstSection.Body.FirstParagraph.RemoveAllChildren();

// 2 - Définissez la forme à lier à un fichier image dans le système de fichiers local.
shape = new Shape(builder.Document, ShapeType.Image);
shape.WrapType = WrapType.Inline;
shape.ImageData.SourceFullName = imageFileName;

builder.InsertNode(shape);
doc.Save(ArtifactsDir + "Image.CreateLinkedImage.Linked.docx");

// La création de liens vers des images permet d'économiser de l'espace et d'obtenir un document plus petit.
// Cependant, le document ne peut afficher correctement l'image que lorsque
// le fichier image est présent à l'emplacement vers lequel pointe la propriété "SourceFullName" de la forme.
Assert.True(10000 > new FileInfo(ArtifactsDir + "Image.CreateLinkedImage.Linked.docx").Length);
```

### Voir également

* class [ImageData](../../imagedata/)
* class [Shape](../)
* espace de noms [Aspose.Words.Drawing](../../shape/)
* Assemblée [Aspose.Words](../../../)


