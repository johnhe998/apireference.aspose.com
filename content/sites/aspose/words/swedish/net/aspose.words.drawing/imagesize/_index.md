---
title: Class ImageSize
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.Drawing.ImageSize klass. Innehåller information om bildstorlek och upplösning.
type: docs
weight: 940
url: /sv/net/aspose.words.drawing/imagesize/
---
## ImageSize class

Innehåller information om bildstorlek och upplösning.

```csharp
public class ImageSize
```

## Konstruktörer

| namn | Beskrivning |
| --- | --- |
| [ImageSize](imagesize/#constructor)(int, int) | Initierar bredd och höjd till de givna värdena i pixlar. Initierar upplösning till 96 dpi. |
| [ImageSize](imagesize/#constructor_1)(int, int, double, double) | Initierar bredd, höjd och upplösning till de givna värdena. |

## Egenskaper

| namn | Beskrivning |
| --- | --- |
| [HeightPixels](../../aspose.words.drawing/imagesize/heightpixels/) { get; } | Får bildens höjd i pixlar. |
| [HeightPoints](../../aspose.words.drawing/imagesize/heightpoints/) { get; } | Får bildens höjd i poäng. 1 poäng är 1/72 tum. |
| [HorizontalResolution](../../aspose.words.drawing/imagesize/horizontalresolution/) { get; } | Får den horisontella upplösningen i DPI. |
| [VerticalResolution](../../aspose.words.drawing/imagesize/verticalresolution/) { get; } | Får den vertikala upplösningen i DPI. |
| [WidthPixels](../../aspose.words.drawing/imagesize/widthpixels/) { get; } | Hämtar bildens bredd i pixlar. |
| [WidthPoints](../../aspose.words.drawing/imagesize/widthpoints/) { get; } | Hämtar bildens bredd i punkter. 1 poäng är 1/72 tum. |

### Exempel

Visar hur man ändrar storlek på en form med en bild.

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

            // När vi infogar en bild med metoden "InsertImage" skalar byggaren formen som visar bilden så att,
            // när vi visar dokumentet med 100 % zoom i Microsoft Word, visar formen bilden i dess verkliga storlek.
            Document doc = new Document();
            DocumentBuilder builder = new DocumentBuilder(doc);
            Shape shape = builder.InsertImage(ImageDir + "Logo.jpg");

            // En bild på 400x400 skapar ett ImageData-objekt med en bildstorlek på 300x300pt.
            ImageSize imageSize = shape.ImageData.ImageSize;

            Assert.AreEqual(300.0d, imageSize.WidthPoints);
            Assert.AreEqual(300.0d, imageSize.HeightPoints);

            // Om en forms mått matchar bilddatas mått,
            // då visar formen bilden i sin ursprungliga storlek.
            Assert.AreEqual(300.0d, shape.Width);
            Assert.AreEqual(300.0d, shape.Height);

              // Minska formens totala storlek med 50 %.
            shape.Width *= 0.5;

              // Skalningsfaktorer gäller för både bredden och höjden samtidigt för att bevara formens proportioner.
            Assert.AreEqual(150.0d, shape.Width);
            Assert.AreEqual(150.0d, shape.Height);

            // När vi ändrar storlek på formen förblir storleken på bilddata densamma.
            Assert.AreEqual(300.0d, imageSize.WidthPoints);
            Assert.AreEqual(300.0d, imageSize.HeightPoints);

            // Vi kan referera till bilddatadimensionerna för att tillämpa en skalning baserat på bildens storlek.
            shape.Width = imageSize.WidthPoints * 1.1;

            Assert.AreEqual(330.0d, shape.Width);
            Assert.AreEqual(330.0d, shape.Height);

            doc.Save(ArtifactsDir + "Image.ScaleImage.docx");
```

### Se även

* property [ImageSize](../imagedata/imagesize/)
* namnutrymme [Aspose.Words.Drawing](../../aspose.words.drawing/)
* hopsättning [Aspose.Words](../../)


