---
title: Class ImageSize
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Drawing.ImageSize klas. Enthält Informationen zu Bildgröße und Auflösung.
type: docs
weight: 940
url: /de/net/aspose.words.drawing/imagesize/
---
## ImageSize class

Enthält Informationen zu Bildgröße und Auflösung.

```csharp
public class ImageSize
```

## Konstrukteure

| Name | Beschreibung |
| --- | --- |
| [ImageSize](imagesize/#constructor)(int, int) | Initialisiert Breite und Höhe auf die angegebenen Werte in Pixel. Initialisiert die Auflösung auf 96 dpi. |
| [ImageSize](imagesize/#constructor_1)(int, int, double, double) | Initialisiert Breite, Höhe und Auflösung auf die angegebenen Werte. |

## Eigenschaften

| Name | Beschreibung |
| --- | --- |
| [HeightPixels](../../aspose.words.drawing/imagesize/heightpixels/) { get; } | Ruft die Höhe des Bildes in Pixel ab. |
| [HeightPoints](../../aspose.words.drawing/imagesize/heightpoints/) { get; } | Ruft die Höhe des Bildes in Punkten ab. 1 Punkt ist 1/72 Zoll. |
| [HorizontalResolution](../../aspose.words.drawing/imagesize/horizontalresolution/) { get; } | Ruft die horizontale Auflösung in DPI ab. |
| [VerticalResolution](../../aspose.words.drawing/imagesize/verticalresolution/) { get; } | Ruft die vertikale Auflösung in DPI ab. |
| [WidthPixels](../../aspose.words.drawing/imagesize/widthpixels/) { get; } | Ruft die Breite des Bildes in Pixel ab. |
| [WidthPoints](../../aspose.words.drawing/imagesize/widthpoints/) { get; } | Ruft die Breite des Bildes in Punkten ab. 1 Punkt ist 1/72 Zoll. |

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

* property [ImageSize](../imagedata/imagesize/)
* namensraum [Aspose.Words.Drawing](../../aspose.words.drawing/)
* Montage [Aspose.Words](../../)


