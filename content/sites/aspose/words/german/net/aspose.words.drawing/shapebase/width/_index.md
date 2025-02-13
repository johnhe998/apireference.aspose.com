---
title: ShapeBase.Width
second_title: Aspose.Words für .NET-API-Referenz
description: ShapeBase eigendom. Ruft die Breite des umschließenden Blocks der Form ab oder legt sie fest.
type: docs
weight: 520
url: /de/net/aspose.words.drawing/shapebase/width/
---
## ShapeBase.Width property

Ruft die Breite des umschließenden Blocks der Form ab oder legt sie fest.

```csharp
public double Width { get; set; }
```

### Bemerkungen

Für eine Form der obersten Ebene wird der Wert in Punkten angegeben.

Bei Formen in einer Gruppe befindet sich der Wert im Koordinatenraum und in den Einheiten der übergeordneten Gruppe.

Der Standardwert ist 0.

### Beispiele

Zeigt, wie Sie ein schwebendes Bild einfügen und seine Position und Größe angeben.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertImage(ImageDir + "Logo.jpg");
shape.WrapType = WrapType.None;

// Konfigurieren Sie die Eigenschaft "RelativeHorizontalPosition" der Form, um den Wert der Eigenschaft "Left" zu behandeln
 // als horizontaler Abstand der Form in Punkten von der linken Seite der Seite.
shape.RelativeHorizontalPosition = RelativeHorizontalPosition.Page;

// Legen Sie den horizontalen Abstand der Form von der linken Seite der Seite auf 100 fest.
shape.Left = 100;

// Verwenden Sie die Eigenschaft "RelativeVerticalPosition" auf ähnliche Weise, um die Form 80 pt unter dem oberen Rand der Seite zu positionieren.
shape.RelativeVerticalPosition = RelativeVerticalPosition.Page;
shape.Top = 80;

// Legen Sie die Höhe der Form fest, wodurch die Breite automatisch skaliert wird, um die Abmessungen beizubehalten.
shape.Height = 125;

Assert.AreEqual(125.0d, shape.Width);

// Die Eigenschaften "Bottom" und "Right" enthalten den unteren und rechten Rand des Bildes.
Assert.AreEqual(shape.Top + shape.Height, shape.Bottom);
Assert.AreEqual(shape.Left + shape.Width, shape.Right);

doc.Save(ArtifactsDir + "Image.CreateFloatingPositionSize.docx");
```

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

* class [ShapeBase](../)
* namensraum [Aspose.Words.Drawing](../../shapebase/)
* Montage [Aspose.Words](../../../)


