---
title: ImageSize.WidthPixels
second_title: Aspose.Words för .NET API Referens
description: ImageSize fast egendom. Hämtar bildens bredd i pixlar.
type: docs
weight: 60
url: /sv/net/aspose.words.drawing/imagesize/widthpixels/
---
## ImageSize.WidthPixels property

Hämtar bildens bredd i pixlar.

```csharp
public int WidthPixels { get; }
```

### Exempel

Visar hur man läser egenskaperna för en bild i en form.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Infoga en form i dokumentet som innehåller en bild tagen från vårt lokala filsystem.
Shape shape = builder.InsertImage(ImageDir + "Logo.jpg");

// Om formen innehåller en bild kommer dess ImageData-egenskap att vara giltig,
// och det kommer att innehålla ett ImageSize-objekt.
ImageSize imageSize = shape.ImageData.ImageSize; 

// ImageSize-objektet innehåller skrivskyddad information om bilden i formen.
Assert.AreEqual(400, imageSize.HeightPixels);
Assert.AreEqual(400, imageSize.WidthPixels);

const double delta = 0.05;
Assert.AreEqual(95.98d, imageSize.HorizontalResolution, delta);
Assert.AreEqual(95.98d, imageSize.VerticalResolution, delta);

// Vi kan basera storleken på formen på storleken på dess bild för att undvika att bilden sträcker ut.
shape.Width = imageSize.WidthPoints * 2;
shape.Height = imageSize.HeightPoints * 2;

doc.Save(ArtifactsDir + "Drawing.ImageSize.docx");
```

### Se även

* class [ImageSize](../)
* namnutrymme [Aspose.Words.Drawing](../../imagesize/)
* hopsättning [Aspose.Words](../../../)


