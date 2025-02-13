---
title: ImageData.ImageSize
second_title: Aspose.Words für .NET-API-Referenz
description: ImageData eigendom. Ruft die Informationen über Bildgröße und Auflösung ab.
type: docs
weight: 130
url: /de/net/aspose.words.drawing/imagedata/imagesize/
---
## ImageData.ImageSize property

Ruft die Informationen über Bildgröße und Auflösung ab.

```csharp
public ImageSize ImageSize { get; }
```

### Bemerkungen

Wenn das Bild nur verlinkt und nicht im Dokument gespeichert ist, wird die Größe Null zurückgegeben.

### Beispiele

Zeigt, wie Sie die Größe einer Form mit einem Bild ändern.

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

            // Wenn wir ein Bild mit der Methode "InsertImage" einfügen, skaliert der Builder die Form, die das Bild anzeigt, so, dass
            // Wenn wir das Dokument mit 100 % Zoom in Microsoft Word anzeigen, zeigt die Form das Bild in seiner tatsächlichen Größe an.
            Document doc = new Document();
            DocumentBuilder builder = new DocumentBuilder(doc);
            Shape shape = builder.InsertImage(ImageDir + "Logo.jpg");

            // Ein 400x400-Bild erstellt ein ImageData-Objekt mit einer Bildgröße von 300x300pt.
            ImageSize imageSize = shape.ImageData.ImageSize;

            Assert.AreEqual(300.0d, imageSize.WidthPoints);
            Assert.AreEqual(300.0d, imageSize.HeightPoints);

            // Wenn die Abmessungen einer Form mit den Abmessungen der Bilddaten übereinstimmen,
            // dann zeigt die Form das Bild in Originalgröße an.
            Assert.AreEqual(300.0d, shape.Width);
            Assert.AreEqual(300.0d, shape.Height);

             // Reduzieren Sie die Gesamtgröße der Form um 50 %.
            shape.Width *= 0.5;

             // Skalierungsfaktoren gelten gleichzeitig für Breite und Höhe, um die Proportionen der Form beizubehalten.
            Assert.AreEqual(150.0d, shape.Width);
            Assert.AreEqual(150.0d, shape.Height);

            // Wenn wir die Größe der Form ändern, bleibt die Größe der Bilddaten gleich.
            Assert.AreEqual(300.0d, imageSize.WidthPoints);
            Assert.AreEqual(300.0d, imageSize.HeightPoints);

            // Wir können auf die Abmessungen der Bilddaten verweisen, um eine Skalierung basierend auf der Größe des Bildes anzuwenden.
            shape.Width = imageSize.WidthPoints * 1.1;

            Assert.AreEqual(330.0d, shape.Width);
            Assert.AreEqual(330.0d, shape.Height);

            doc.Save(ArtifactsDir + "Image.ScaleImage.docx");
```

### Siehe auch

* class [ImageSize](../../imagesize/)
* class [ImageData](../)
* namensraum [Aspose.Words.Drawing](../../imagedata/)
* Montage [Aspose.Words](../../../)


