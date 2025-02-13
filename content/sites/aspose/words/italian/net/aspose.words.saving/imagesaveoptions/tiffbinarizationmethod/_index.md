---
title: ImageSaveOptions.TiffBinarizationMethod
second_title: Aspose.Words per .NET API Reference
description: ImageSaveOptions proprietà. Ottiene o imposta il metodo utilizzato durante la conversione delle immagini in formato 1 bpp quandoSaveFormat è SaveFormat.Tiff e TiffCompression è uguale a TiffCompression.Ccitt3 o TiffCompression.Ccitt4.
type: docs
weight: 160
url: /it/net/aspose.words.saving/imagesaveoptions/tiffbinarizationmethod/
---
## ImageSaveOptions.TiffBinarizationMethod property

Ottiene o imposta il metodo utilizzato durante la conversione delle immagini in formato 1 bpp quando[`SaveFormat`](../saveformat/) è SaveFormat.Tiff e [`TiffCompression`](../tiffcompression/) è uguale a TiffCompression.Ccitt3 o TiffCompression.Ccitt4.

```csharp
public ImageBinarizationMethod TiffBinarizationMethod { get; set; }
```

### Osservazioni

Il valore predefinito è ImageBinarizationMethod.Threshold.

### Esempi

Mostra come impostare la soglia di errore di binarizzazione TIFF quando si utilizza il metodo Floyd-Steinberg per eseguire il rendering di un'immagine TIFF.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ParagraphFormat.Style = doc.Styles["Heading 1"];
builder.Writeln("Hello world!");
builder.InsertImage(ImageDir + "Logo.jpg");

// Quando salviamo il documento come TIFF, possiamo passare un oggetto SaveOptions a
// regola il dithering che Aspose.Words applicherà durante il rendering di questa immagine.
// Il valore predefinito della proprietà "ThresholdForFloydSteinbergDithering" è 128.
// Valori più alti tendono a produrre immagini più scure.
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Tiff)
{
    TiffCompression = TiffCompression.Ccitt3,
    TiffBinarizationMethod = ImageBinarizationMethod.FloydSteinbergDithering,
    ThresholdForFloydSteinbergDithering = 240
};

doc.Save(ArtifactsDir + "ImageSaveOptions.FloydSteinbergDithering.tiff", options);
```

### Guarda anche

* enum [ImageBinarizationMethod](../../imagebinarizationmethod/)
* class [ImageSaveOptions](../)
* spazio dei nomi [Aspose.Words.Saving](../../imagesaveoptions/)
* assemblea [Aspose.Words](../../../)


