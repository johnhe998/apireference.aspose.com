---
title: ImageSaveOptions.SaveFormat
second_title: Aspose.Words per .NET API Reference
description: ImageSaveOptions proprietà. Specifica il formato in cui verranno salvate le pagine o le forme del documento renderizzate se viene utilizzato questo oggetto delle opzioni di salvataggio. Può essere un raster Tiff Png Bmp  Jpeg o vettoreEmf Svg .
type: docs
weight: 130
url: /it/net/aspose.words.saving/imagesaveoptions/saveformat/
---
## ImageSaveOptions.SaveFormat property

Specifica il formato in cui verranno salvate le pagine o le forme del documento renderizzate se viene utilizzato questo oggetto delle opzioni di salvataggio. Può essere un raster Tiff ,Png ,Bmp , Jpeg o vettoreEmf ,Svg .

```csharp
public override SaveFormat SaveFormat { get; set; }
```

### Osservazioni

Su piattaforme diverse, i formati supportati potrebbero essere diversi. Il numero di altre opzioni dipende dal formato selezionato.

Inoltre, è possibile salvare in SVG sia tramite ImageSaveOptions che tramite[`SvgSaveOptions`](../../svgsaveoptions/).

### Esempi

Mostra come modificare l'immagine mentre Aspose.Words converte un documento in uno.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ParagraphFormat.Style = doc.Styles["Heading 1"];
builder.Writeln("Hello world!");
builder.InsertImage(ImageDir + "Logo.jpg");

// Quando salviamo il documento come immagine, possiamo passare un oggetto SaveOptions a
// modifica l'immagine mentre l'operazione di salvataggio la rende.
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Png)
{
    // Possiamo regolare queste proprietà per cambiare la luminosità e il contrasto dell'immagine.
    // Entrambi sono su una scala 0-1 e sono a 0,5 per impostazione predefinita.
    ImageBrightness = 0.3f,
    ImageContrast = 0.7f,

    // Possiamo regolare la risoluzione orizzontale e verticale con queste proprietà.
    // Ciò influenzerà le dimensioni dell'immagine.
    // Il valore predefinito per queste proprietà è 96.0, per una risoluzione di 96 dpi.
    HorizontalResolution = 72f,
    VerticalResolution = 72f,

    // Possiamo ridimensionare l'immagine usando questa proprietà. Il valore predefinito è 1,0, per un ridimensionamento del 100%.
    // Possiamo usare questa proprietà per negare qualsiasi cambiamento nelle dimensioni dell'immagine che potrebbe causare la modifica della risoluzione.
    Scale = 96f / 72f
};

doc.Save(ArtifactsDir + "ImageSaveOptions.EditImage.png", options);
```

### Guarda anche

* enum [SaveFormat](../../../aspose.words/saveformat/)
* class [ImageSaveOptions](../)
* spazio dei nomi [Aspose.Words.Saving](../../imagesaveoptions/)
* assemblea [Aspose.Words](../../../)


