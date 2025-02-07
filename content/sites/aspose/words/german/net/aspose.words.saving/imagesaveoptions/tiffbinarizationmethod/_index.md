---
title: ImageSaveOptions.TiffBinarizationMethod
second_title: Aspose.Words für .NET-API-Referenz
description: ImageSaveOptions eigendom. Ruft die Methode ab oder legt sie fest die beim Konvertieren von Bildern in das 1bppFormat wann verwendet wirdSaveFormat ist SaveFormat.Tiff and TiffCompression ist gleich TiffCompression.Ccitt3 oder TiffCompression.Ccitt4.
type: docs
weight: 160
url: /de/net/aspose.words.saving/imagesaveoptions/tiffbinarizationmethod/
---
## ImageSaveOptions.TiffBinarizationMethod property

Ruft die Methode ab oder legt sie fest, die beim Konvertieren von Bildern in das 1-bpp-Format wann verwendet wird[`SaveFormat`](../saveformat/) ist SaveFormat.Tiff and [`TiffCompression`](../tiffcompression/) ist gleich TiffCompression.Ccitt3 oder TiffCompression.Ccitt4.

```csharp
public ImageBinarizationMethod TiffBinarizationMethod { get; set; }
```

### Bemerkungen

Der Standardwert ist ImageBinarizationMethod.Threshold.

### Beispiele

Zeigt, wie der TIFF-Binärisierungsfehlerschwellenwert festgelegt wird, wenn die Floyd-Steinberg-Methode zum Rendern eines TIFF-Bilds verwendet wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ParagraphFormat.Style = doc.Styles["Heading 1"];
builder.Writeln("Hello world!");
builder.InsertImage(ImageDir + "Logo.jpg");

// Wenn wir das Dokument als TIFF speichern, können wir ein SaveOptions-Objekt an übergeben
// Passen Sie das Dithering an, das Aspose.Words beim Rendern dieses Bildes anwendet.
// Der Standardwert der Eigenschaft "ThresholdForFloydSteinbergDithering" ist 128.
// Höhere Werte führen tendenziell zu dunkleren Bildern.
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Tiff)
{
    TiffCompression = TiffCompression.Ccitt3,
    TiffBinarizationMethod = ImageBinarizationMethod.FloydSteinbergDithering,
    ThresholdForFloydSteinbergDithering = 240
};

doc.Save(ArtifactsDir + "ImageSaveOptions.FloydSteinbergDithering.tiff", options);
```

### Siehe auch

* enum [ImageBinarizationMethod](../../imagebinarizationmethod/)
* class [ImageSaveOptions](../)
* namensraum [Aspose.Words.Saving](../../imagesaveoptions/)
* Montage [Aspose.Words](../../../)


