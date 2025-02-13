---
title: Enum ImageColorMode
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Saving.ImageColorMode opsomming. Gibt den Farbmodus für die generierten Bilder von Dokumentseiten an.
type: docs
weight: 4950
url: /de/net/aspose.words.saving/imagecolormode/
---
## ImageColorMode enumeration

Gibt den Farbmodus für die generierten Bilder von Dokumentseiten an.

```csharp
public enum ImageColorMode
```

### Werte

| Name | Wert | Beschreibung |
| --- | --- | --- |
| None | `0` | Die Seiten des Dokuments werden als Farbbilder gerendert. |
| Grayscale | `1` | Die Seiten des Dokuments werden als Graustufenbilder gerendert. |
| BlackAndWhite | `2` | Die Seiten des Dokuments werden als Schwarzweißbilder gerendert. |

### Beispiele

Zeigt, wie beim Rendern von Dokumenten ein Farbmodus festgelegt wird.

```csharp
Document doc = new Document();
            DocumentBuilder builder = new DocumentBuilder(doc);

            builder.ParagraphFormat.Style = doc.Styles["Heading 1"];
            builder.Writeln("Hello world!");
            builder.InsertImage(ImageDir + "Logo.jpg");

            Assert.That(20000, Is.LessThan(new FileInfo(ImageDir + "Logo.jpg").Length));

            // Wenn wir das Dokument als Bild speichern, können wir ein SaveOptions-Objekt an übergeben
            // Wählen Sie einen Farbmodus für das Bild aus, das der Speichervorgang erzeugen wird.
            // Wenn wir die Eigenschaft "ImageColorMode" auf "ImageColorMode.BlackAndWhite" setzen,
            // Der Speichervorgang wendet beim Rendern des Dokuments eine Graustufen-Farbreduzierung an.
             // Wenn wir die Eigenschaft "ImageColorMode" auf "ImageColorMode.Grayscale" setzen,
            // Der Speichervorgang wird das Dokument in ein monochromes Bild umwandeln.
            // Wenn wir die Eigenschaft "ImageColorMode" auf "None" setzen, wendet der Speichervorgang die Standardmethode an
            // und alle Farben des Dokuments im Ausgabebild beibehalten.
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

### Siehe auch

* namensraum [Aspose.Words.Saving](../../aspose.words.saving/)
* Montage [Aspose.Words](../../)


