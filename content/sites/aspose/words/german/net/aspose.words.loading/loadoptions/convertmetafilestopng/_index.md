---
title: LoadOptions.ConvertMetafilesToPng
second_title: Aspose.Words für .NET-API-Referenz
description: LoadOptions eigendom. Ruft ab oder legt fest ob Metadatei konvertiert werden soll Wmf oderEmf  Bilder zuPng Bildformat.
type: docs
weight: 30
url: /de/net/aspose.words.loading/loadoptions/convertmetafilestopng/
---
## LoadOptions.ConvertMetafilesToPng property

Ruft ab oder legt fest, ob Metadatei konvertiert werden soll (Wmf oderEmf ) Bilder zuPng Bildformat.

```csharp
public bool ConvertMetafilesToPng { get; set; }
```

### Bemerkungen

Metadateien (Wmf oderEmf ) ist ein unkomprimiertes Bildformat und benötigt manchmal zu viel RAM, um das Dokument zu speichern und zu verarbeiten. Mit dieser Option können alle Metafile-Bilder in konvertiert werdenPng beim Laden des Dokuments. Bitte beachten Sie - die Umwandlung von Vektorgrafiken in Raster verringert die Qualität der Bilder.

### Beispiele

Zeigt, wie WMF/EMF beim Laden des Dokuments in PNG konvertiert wird.

```csharp
Document doc = new Document();

            Shape shape = new Shape(doc, ShapeType.Image);
            shape.ImageData.SetImage(ImageDir + "Windows MetaFile.wmf");
            shape.Width = 100;
            shape.Height = 100;

            doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

            doc.Save(ArtifactsDir + "Image.CreateImageDirectly.docx");

            shape = (Shape)doc.GetChild(NodeType.Shape, 0, true);

            TestUtil.VerifyImageInShape(1600, 1600, ImageType.Wmf, shape);

            LoadOptions loadOptions = new LoadOptions();
            loadOptions.ConvertMetafilesToPng = true;

            doc = new Document(ArtifactsDir + "Image.CreateImageDirectly.docx", loadOptions);
            shape = (Shape)doc.GetChild(NodeType.Shape, 0, true);

#if NET48
            TestUtil.VerifyImageInShape(1666, 1666, ImageType.Png, shape);
#elif NET5_0_OR_GREATER
            TestUtil.VerifyImageInShape(1666, 1666, ImageType.Png, shape);
#endif
```

### Siehe auch

* class [LoadOptions](../)
* namensraum [Aspose.Words.Loading](../../loadoptions/)
* Montage [Aspose.Words](../../../)


