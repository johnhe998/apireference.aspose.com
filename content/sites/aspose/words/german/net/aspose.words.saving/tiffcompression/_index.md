---
title: Enum TiffCompression
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Saving.TiffCompression opsomming. Gibt an welcher Komprimierungstyp angewendet werden soll wenn Seitenbilder in einer TIFFDatei gespeichert werden.
type: docs
weight: 5350
url: /de/net/aspose.words.saving/tiffcompression/
---
## TiffCompression enumeration

Gibt an, welcher Komprimierungstyp angewendet werden soll, wenn Seitenbilder in einer TIFF-Datei gespeichert werden.

```csharp
public enum TiffCompression
```

### Werte

| Name | Wert | Beschreibung |
| --- | --- | --- |
| None | `0` | Gibt keine Komprimierung an. |
| Rle | `1` | Gibt das RLE-Komprimierungsschema an. |
| Lzw | `2` | Gibt das LZW-Komprimierungsschema an. In Java emuliert durch Deflate (Zip)-Komprimierung. |
| Ccitt3 | `3` | Gibt das CCITT3-Komprimierungsschema an. |
| Ccitt4 | `4` | Gibt das CCITT4-Komprimierungsschema an. |

### Beispiele

Zeigt, wie Sie das Komprimierungsschema auswählen, das auf ein Dokument angewendet werden soll, das wir in ein TIFF-Bild konvertieren.

```csharp
Document doc = new Document();
            DocumentBuilder builder = new DocumentBuilder(doc);

            builder.InsertImage(ImageDir + "Logo.jpg");

            // Erstellen Sie ein "ImageSaveOptions"-Objekt, das wir an die "Save"-Methode des Dokuments übergeben können
            // um die Art und Weise zu ändern, in der diese Methode das Dokument in ein Bild rendert.
            ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Tiff);

            // Setzen Sie die Eigenschaft "TiffCompression" auf "TiffCompression.None", um beim Speichern keine Komprimierung anzuwenden,
            // was zu einer sehr großen Ausgabedatei führen kann.
            // Legen Sie die Eigenschaft "TiffCompression" auf "TiffCompression.Rle" fest, um die RLE-Komprimierung anzuwenden
            // Legen Sie die Eigenschaft "TiffCompression" auf "TiffCompression.Lzw" fest, um die LZW-Komprimierung anzuwenden.
            // Legen Sie die Eigenschaft "TiffCompression" auf "TiffCompression.Ccitt3" fest, um die CCITT3-Komprimierung anzuwenden.
            // Legen Sie die Eigenschaft "TiffCompression" auf "TiffCompression.Ccitt4" fest, um die CCITT4-Komprimierung anzuwenden.
            options.TiffCompression = tiffCompression;

            doc.Save(ArtifactsDir + "ImageSaveOptions.TiffImageCompression.tiff", options);

            switch (tiffCompression)
            {
                case TiffCompression.None:
                    Assert.That(3000000, Is.LessThan(new FileInfo(ArtifactsDir + "ImageSaveOptions.TiffImageCompression.tiff").Length));
                    break;
                case TiffCompression.Rle:
#if NET5_0_OR_GREATER
                    Assert.That(6000, Is.LessThan(new FileInfo(ArtifactsDir + "ImageSaveOptions.TiffImageCompression.tiff").Length));
#else
                    Assert.That(600000, Is.LessThan(new FileInfo(ArtifactsDir + "ImageSaveOptions.TiffImageCompression.tiff").Length));
#endif
                    break;
                case TiffCompression.Lzw:
                    Assert.That(200000, Is.LessThan(new FileInfo(ArtifactsDir + "ImageSaveOptions.TiffImageCompression.tiff").Length));
                    break;
                case TiffCompression.Ccitt3:
                    Assert.That(90000, Is.AtLeast(new FileInfo(ArtifactsDir + "ImageSaveOptions.TiffImageCompression.tiff").Length));
                    break;
                case TiffCompression.Ccitt4:
                    Assert.That(20000, Is.AtLeast(new FileInfo(ArtifactsDir + "ImageSaveOptions.TiffImageCompression.tiff").Length));
                    break;
            }
```

### Siehe auch

* namensraum [Aspose.Words.Saving](../../aspose.words.saving/)
* Montage [Aspose.Words](../../)


