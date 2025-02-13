---
title: Enum ImageBinarizationMethod
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Saving.ImageBinarizationMethod enum. Specifica il metodo utilizzato per binarizzare limmagine.
type: docs
weight: 4940
url: /it/net/aspose.words.saving/imagebinarizationmethod/
---
## ImageBinarizationMethod enumeration

Specifica il metodo utilizzato per binarizzare l'immagine.

```csharp
public enum ImageBinarizationMethod
```

### I valori

| Nome | Valore | Descrizione |
| --- | --- | --- |
| Threshold | `0` | Specifica il metodo di soglia. |
| FloydSteinbergDithering | `1` | Specifica il dithering utilizzando il metodo di diffusione degli errori di Floyd-Steinberg. |

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

* spazio dei nomi [Aspose.Words.Saving](../../aspose.words.saving/)
* assemblea [Aspose.Words](../../)


