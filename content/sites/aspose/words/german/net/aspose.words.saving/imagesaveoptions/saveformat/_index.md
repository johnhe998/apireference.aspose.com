---
title: ImageSaveOptions.SaveFormat
second_title: Aspose.Words für .NET-API-Referenz
description: ImageSaveOptions eigendom. Gibt das Format an in dem die gerenderten Dokumentseiten oder formen gespeichert werden wenn dieses Speicheroptionsobjekt verwendet wird. Kann ein Raster sein Tiff Png Bmp  Jpeg oder VektorEmf Svg .
type: docs
weight: 130
url: /de/net/aspose.words.saving/imagesaveoptions/saveformat/
---
## ImageSaveOptions.SaveFormat property

Gibt das Format an, in dem die gerenderten Dokumentseiten oder -formen gespeichert werden, wenn dieses Speicheroptionsobjekt verwendet wird. Kann ein Raster sein Tiff ,Png ,Bmp , Jpeg oder VektorEmf ,Svg .

```csharp
public override SaveFormat SaveFormat { get; set; }
```

### Bemerkungen

Auf verschiedenen Plattformen können die unterstützten Formate unterschiedlich sein. Die Anzahl der weiteren Optionen hängt vom ausgewählten Format ab.

Außerdem ist es möglich, sowohl über ImageSaveOptions als auch über in SVG zu speichern[`SvgSaveOptions`](../../svgsaveoptions/).

### Beispiele

Zeigt, wie das Bild bearbeitet wird, während Aspose.Words ein Dokument in eins konvertiert.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ParagraphFormat.Style = doc.Styles["Heading 1"];
builder.Writeln("Hello world!");
builder.InsertImage(ImageDir + "Logo.jpg");

// Wenn wir das Dokument als Bild speichern, können wir ein SaveOptions-Objekt an übergeben
// das Bild bearbeiten, während der Speichervorgang es rendert.
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Png)
{
    // Wir können diese Eigenschaften anpassen, um die Helligkeit und den Kontrast des Bildes zu ändern.
    // Beide liegen auf einer Skala von 0-1 und sind standardmäßig bei 0,5.
    ImageBrightness = 0.3f,
    ImageContrast = 0.7f,

    // Mit diesen Eigenschaften können wir die horizontale und vertikale Auflösung anpassen.
    // Dies wirkt sich auf die Abmessungen des Bildes aus.
    // Der Standardwert für diese Eigenschaften ist 96,0 für eine Auflösung von 96 dpi.
    HorizontalResolution = 72f,
    VerticalResolution = 72f,

    // Mit dieser Eigenschaft können wir das Bild skalieren. Der Standardwert ist 1,0 für eine Skalierung von 100 %.
    // Wir können diese Eigenschaft verwenden, um alle Änderungen der Bildabmessungen zu negieren, die eine Änderung der Auflösung verursachen würde.
    Scale = 96f / 72f
};

doc.Save(ArtifactsDir + "ImageSaveOptions.EditImage.png", options);
```

### Siehe auch

* enum [SaveFormat](../../../aspose.words/saveformat/)
* class [ImageSaveOptions](../)
* namensraum [Aspose.Words.Saving](../../imagesaveoptions/)
* Montage [Aspose.Words](../../../)


