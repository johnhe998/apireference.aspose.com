---
title: ImageSaveOptions.Resolution
second_title: Aspose.Words för .NET API Referens
description: ImageSaveOptions fast egendom. Ställer in både horisontell och vertikal upplösning för de genererade bilderna i punkter per tum.
type: docs
weight: 120
url: /sv/net/aspose.words.saving/imagesaveoptions/resolution/
---
## ImageSaveOptions.Resolution property

Ställer in både horisontell och vertikal upplösning för de genererade bilderna, i punkter per tum.

```csharp
public float Resolution { set; }
```

### Anmärkningar

Den här egenskapen har endast effekt när du sparar i rasterbildsformat.

### Exempel

Visar hur man anger en upplösning när ett dokument renderas till PNG.

```csharp
Document doc = new Document();
            DocumentBuilder builder = new DocumentBuilder(doc);

            builder.Font.Name = "Times New Roman";
            builder.Font.Size = 24;
            builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");

            builder.InsertImage(ImageDir + "Logo.jpg");

            // Skapa ett "ImageSaveOptions"-objekt som vi kan skicka till dokumentets "Spara"-metod
            // för att ändra sättet på vilket den metoden renderar dokumentet till en bild.
            ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Png);

            // Ställ in egenskapen "Resolution" till "72" för att återge dokumentet i 72dpi.
            options.Resolution = 72;

            doc.Save(ArtifactsDir + "ImageSaveOptions.Resolution.72dpi.png", options);

            Assert.That(120000, Is.AtLeast(new FileInfo(ArtifactsDir + "ImageSaveOptions.Resolution.72dpi.png").Length));

#if NET48 || JAVA
            Image image = Image.FromFile(ArtifactsDir + "ImageSaveOptions.Resolution.72dpi.png");

            Assert.AreEqual(612, image.Width);
            Assert.AreEqual(792, image.Height);
#elif NET5_0_OR_GREATER || __MOBILE__
            using (SKBitmap image = SKBitmap.Decode(ArtifactsDir + "ImageSaveOptions.Resolution.72dpi.png")) 
            {
                Assert.AreEqual(612, image.Width);
                Assert.AreEqual(792, image.Height);
            }
#endif
            // Ställ in egenskapen "Resolution" till "300" för att återge dokumentet i 300 dpi.
            options.Resolution = 300;

            doc.Save(ArtifactsDir + "ImageSaveOptions.Resolution.300dpi.png", options);

            Assert.That(700000, Is.LessThan(new FileInfo(ArtifactsDir + "ImageSaveOptions.Resolution.300dpi.png").Length));

#if NET48 || JAVA
            image = Image.FromFile(ArtifactsDir + "ImageSaveOptions.Resolution.300dpi.png");

            Assert.AreEqual(2550, image.Width);
            Assert.AreEqual(3300, image.Height);
#elif NET5_0_OR_GREATER || __MOBILE__
            using (SKBitmap image = SKBitmap.Decode(ArtifactsDir + "ImageSaveOptions.Resolution.300dpi.png")) 
            {
                Assert.AreEqual(2550, image.Width);
                Assert.AreEqual(3300, image.Height);
            }
#endif
```

### Se även

* class [ImageSaveOptions](../)
* namnutrymme [Aspose.Words.Saving](../../imagesaveoptions/)
* hopsättning [Aspose.Words](../../../)


