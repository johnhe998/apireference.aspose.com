---
title: ImageSaveOptions.ImageSaveOptions
second_title: Aspose.Words für .NET-API-Referenz
description: ImageSaveOptions constructeur. Initialisiert eine neue Instanz dieser Klasse die verwendet werden kann um gerenderte Bilder in the zu speichern.Tiff Png Bmp  Emf Jpeg oderSvg format. Png Bmp Jpeg oderSvg format.
type: docs
weight: 10
url: /de/net/aspose.words.saving/imagesaveoptions/imagesaveoptions/
---
## ImageSaveOptions constructor

Initialisiert eine neue Instanz dieser Klasse, die verwendet werden kann, um gerenderte Bilder in the zu speichern.Tiff ,Png ,Bmp , Emf ,Jpeg oderSvg format. Png ,Bmp ,Jpeg oderSvg format.

```csharp
public ImageSaveOptions(SaveFormat saveFormat)
```

| Parameter | Typ | Beschreibung |
| --- | --- | --- |
| saveFormat | SaveFormat | Kann seinTiff ,Png ,Bmp , Emf ,Jpeg oderSvg . Png ,Bmp ,Jpeg oderSvg . |

### Beispiele

Zeigt, wie die Komprimierung konfiguriert wird, während ein Dokument als JPEG gespeichert wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertImage(ImageDir + "Logo.jpg");

// Erstellen Sie ein "ImageSaveOptions"-Objekt, das wir an die "Save"-Methode des Dokuments übergeben können
// um die Art und Weise zu ändern, in der diese Methode das Dokument in ein Bild rendert.
ImageSaveOptions imageOptions = new ImageSaveOptions(SaveFormat.Jpeg);

// Setzen Sie die Eigenschaft "JpegQuality" auf "10", um beim Rendern des Dokuments eine stärkere Komprimierung zu verwenden.
// Dadurch wird die Dateigröße des Dokuments reduziert, aber das Bild zeigt deutlichere Komprimierungsartefakte.
imageOptions.JpegQuality = 10;

doc.Save(ArtifactsDir + "ImageSaveOptions.JpegQuality.HighCompression.jpg", imageOptions);

Assert.That(20000, Is.AtLeast(new FileInfo(ArtifactsDir + "ImageSaveOptions.JpegQuality.HighCompression.jpg").Length));

// Legen Sie die Eigenschaft "JpegQuality" auf "100" fest, um beim Rendern des Dokuments eine schwächere Komprimierung zu verwenden.
// Dadurch wird die Bildqualität auf Kosten einer erhöhten Dateigröße verbessert.
imageOptions.JpegQuality = 100;

doc.Save(ArtifactsDir + "ImageSaveOptions.JpegQuality.HighQuality.jpg", imageOptions);

Assert.That(60000, Is.LessThan(new FileInfo(ArtifactsDir + "ImageSaveOptions.JpegQuality.HighQuality.jpg").Length));
```

### Siehe auch

* enum [SaveFormat](../../../aspose.words/saveformat/)
* class [ImageSaveOptions](../)
* namensraum [Aspose.Words.Saving](../../imagesaveoptions/)
* Montage [Aspose.Words](../../../)


