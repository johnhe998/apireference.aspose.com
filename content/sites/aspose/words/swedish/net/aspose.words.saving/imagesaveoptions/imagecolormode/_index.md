---
title: ImageSaveOptions.ImageColorMode
second_title: Aspose.Words för .NET API Referens
description: ImageSaveOptions fast egendom. Hämtar eller ställer in färgläget för de genererade bilderna.
type: docs
weight: 50
url: /sv/net/aspose.words.saving/imagesaveoptions/imagecolormode/
---
## ImageSaveOptions.ImageColorMode property

Hämtar eller ställer in färgläget för de genererade bilderna.

```csharp
public ImageColorMode ImageColorMode { get; set; }
```

### Anmärkningar

Den här egenskapen har endast effekt när du sparar i rasterbildsformat.

Standardvärdet ärNone.

### Exempel

Visar hur du ställer in ett färgläge när du renderar dokument.

```csharp
Document doc = new Document();
            DocumentBuilder builder = new DocumentBuilder(doc);

            builder.ParagraphFormat.Style = doc.Styles["Heading 1"];
            builder.Writeln("Hello world!");
            builder.InsertImage(ImageDir + "Logo.jpg");

            Assert.That(20000, Is.LessThan(new FileInfo(ImageDir + "Logo.jpg").Length));

            // När vi sparar dokumentet som en bild kan vi skicka ett SaveOptions-objekt till
            // välj ett färgläge för bilden som sparas.
            // Om vi ställer in egenskapen "ImageColorMode" till "ImageColorMode.BlackAndWhite",
            // sparoperationen kommer att tillämpa gråskalefärgreduktion medan dokumentet renderas.
              // Om vi ställer in egenskapen "ImageColorMode" till "ImageColorMode.Grayscale",
            // sparoperationen kommer att göra dokumentet till en monokrom bild.
            // Om vi ställer in egenskapen "ImageColorMode" till "None", kommer sparoperationen att tillämpa standardmetoden
            // och bevara alla dokumentets färger i utdatabilden.
            ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png);
            imageSaveOptions.ImageColorMode = imageColorMode;

            doc.Save(ArtifactsDir + "ImageSaveOptions.ColorMode.png", imageSaveOptions);

#if NET48 || JAVA
            switch (imageColorMode)
            {
                case ImageColorMode.None:
                    Assert.That(150000, Is.LessThan(new FileInfo(ArtifactsDir + "ImageSaveOptions.ColorMode.png").Length));
                    break;
                case ImageColorMode.Grayscale:
                    Assert.That(80000, Is.LessThan(new FileInfo(ArtifactsDir + "ImageSaveOptions.ColorMode.png").Length));
                    break;
                case ImageColorMode.BlackAndWhite:
                    Assert.That(20000, Is.AtLeast(new FileInfo(ArtifactsDir + "ImageSaveOptions.ColorMode.png").Length));
                    break;
            }
#elif NET5_0_OR_GREATER
            switch (imageColorMode)
            {
                case ImageColorMode.None:
                    Assert.That(120000, Is.LessThan(new FileInfo(ArtifactsDir + "ImageSaveOptions.ColorMode.png").Length));
                    break;
                case ImageColorMode.Grayscale:
                    Assert.That(80000, Is.LessThan(new FileInfo(ArtifactsDir + "ImageSaveOptions.ColorMode.png").Length));
                    break;
                case ImageColorMode.BlackAndWhite:
                    Assert.That(20000, Is.AtLeast(new FileInfo(ArtifactsDir + "ImageSaveOptions.ColorMode.png").Length));
                    break;
            }
#endif
```

### Se även

* enum [ImageColorMode](../../imagecolormode/)
* class [ImageSaveOptions](../)
* namnutrymme [Aspose.Words.Saving](../../imagesaveoptions/)
* hopsättning [Aspose.Words](../../../)


