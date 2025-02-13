---
title: ImageSaveOptions.MetafileRenderingOptions
second_title: Aspose.Words für .NET-API-Referenz
description: ImageSaveOptions eigendom. Ermöglicht festzulegen wie Metadateien in der gerenderten Ausgabe behandelt werden.
type: docs
weight: 80
url: /de/net/aspose.words.saving/imagesaveoptions/metafilerenderingoptions/
---
## ImageSaveOptions.MetafileRenderingOptions property

Ermöglicht festzulegen, wie Metadateien in der gerenderten Ausgabe behandelt werden.

```csharp
public MetafileRenderingOptions MetafileRenderingOptions { get; }
```

### Bemerkungen

WannVector angegeben ist, rendert Aspose.Words -Metadatei mithilfe seiner eigenen Metadatei-Rendering-Engine zuerst in Vektorgrafiken und rendert dann vector -Grafiken in das Bild.

WannBitmap angegeben ist, wird Aspose.Words renders -Metadatei mithilfe der GDI+-Metadatei-Rendering-Engine direkt in das Bild eingefügt.

Die GDI+-Metadatei-Rendering-Engine arbeitet schneller, unterstützt fast alle Metadateifunktionen, aber bei niedrigen -Auflösungen kann es zu inkonsistenten Ergebnissen im Vergleich zum Rest der Vektorgrafiken (insbesondere für Text) auf der Seite kommen. Die Aspose.Words-Metadatei-Rendering-Engine erzeugt bei niedrigen Auflösungen ein konsistenteres Ergebnis even , arbeitet jedoch langsamer und kann komplexe Metadateien ungenau rendern.

Der Standardwert für[`MetafileRenderingMode`](../../metafilerenderingmode/) istBitmap.

### Beispiele

Zeigt, wie Sie den Wiedergabemodus festlegen, wenn Sie Dokumente mit Windows Metafile-Bildern in anderen Bildformaten speichern.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertImage(Image.FromFile(ImageDir + "Windows MetaFile.wmf"));

// Wenn wir das Dokument als Bild speichern, können wir ein SaveOptions-Objekt an übergeben
// bestimmen, wie der Speichervorgang Windows-Metadateien im Dokument verarbeitet.
// Wenn wir die Eigenschaft "RenderingMode" auf "MetafileRenderingMode.Vector" setzen,
// oder "MetafileRenderingMode.VectorWithFallback", wir rendern alle Metadateien als Vektorgrafiken.
// Wenn wir die Eigenschaft "RenderingMode" auf "MetafileRenderingMode.Bitmap" setzen, rendern wir alle Metadateien als Bitmaps.
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Png);
options.MetafileRenderingOptions.RenderingMode = metafileRenderingMode;

doc.Save(ArtifactsDir + "ImageSaveOptions.WindowsMetaFile.png", options);
```

### Siehe auch

* class [MetafileRenderingOptions](../../metafilerenderingoptions/)
* class [ImageSaveOptions](../)
* namensraum [Aspose.Words.Saving](../../imagesaveoptions/)
* Montage [Aspose.Words](../../../)


