---
title: ImageData.ImageSize
second_title: Référence de l'API Aspose.Words pour .NET
description: ImageData propriété. Obtient les informations sur la taille et la résolution de limage.
type: docs
weight: 130
url: /fr/net/aspose.words.drawing/imagedata/imagesize/
---
## ImageData.ImageSize property

Obtient les informations sur la taille et la résolution de l'image.

```csharp
public ImageSize ImageSize { get; }
```

### Remarques

Si l'image est uniquement liée et n'est pas stockée dans le document, renvoie une taille nulle.

### Exemples

Montre comment redimensionner une forme avec une image.

```csharp
#if NET48 || JAVA
            Image image = Image.FromFile(ImageDir + "Logo.jpg");

            Assert.AreEqual(400, image.Size.Width);
            Assert.AreEqual(400, image.Size.Height);
#elif NET5_0_OR_GREATER
            SKBitmap image = SKBitmap.Decode(ImageDir + "Logo.jpg");

            Assert.AreEqual(400, image.Width);
            Assert.AreEqual(400, image.Height);
#endif

            // Lorsque nous insérons une image à l'aide de la méthode "InsertImage", le constructeur redimensionne la forme qui affiche l'image de sorte que,
            // lorsque nous visualisons le document en utilisant un zoom de 100 % dans Microsoft Word, la forme affiche l'image dans sa taille réelle.
            Document doc = new Document();
            DocumentBuilder builder = new DocumentBuilder(doc);
            Shape shape = builder.InsertImage(ImageDir + "Logo.jpg");

            // Une image 400x400 créera un objet ImageData avec une taille d'image de 300x300pt.
            ImageSize imageSize = shape.ImageData.ImageSize;

            Assert.AreEqual(300.0d, imageSize.WidthPoints);
            Assert.AreEqual(300.0d, imageSize.HeightPoints);

            // Si les dimensions d'une forme correspondent aux dimensions des données de l'image,
            // alors la forme affiche l'image dans sa taille d'origine.
            Assert.AreEqual(300.0d, shape.Width);
            Assert.AreEqual(300.0d, shape.Height);

             // Réduit la taille globale de la forme de 50 %.
            shape.Width *= 0.5;

             // Les facteurs d'échelle s'appliquent à la fois à la largeur et à la hauteur pour préserver les proportions de la forme.
            Assert.AreEqual(150.0d, shape.Width);
            Assert.AreEqual(150.0d, shape.Height);

            // Lorsque nous redimensionnons la forme, la taille des données de l'image reste la même.
            Assert.AreEqual(300.0d, imageSize.WidthPoints);
            Assert.AreEqual(300.0d, imageSize.HeightPoints);

            // Nous pouvons référencer les dimensions des données de l'image pour appliquer une mise à l'échelle basée sur la taille de l'image.
            shape.Width = imageSize.WidthPoints * 1.1;

            Assert.AreEqual(330.0d, shape.Width);
            Assert.AreEqual(330.0d, shape.Height);

            doc.Save(ArtifactsDir + "Image.ScaleImage.docx");
```

### Voir également

* class [ImageSize](../../imagesize/)
* class [ImageData](../)
* espace de noms [Aspose.Words.Drawing](../../imagedata/)
* Assemblée [Aspose.Words](../../../)


