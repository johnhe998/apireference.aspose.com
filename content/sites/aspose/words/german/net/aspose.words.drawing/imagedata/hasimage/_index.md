---
title: ImageData.HasImage
second_title: Aspose.Words für .NET-API-Referenz
description: ImageData eigendom. Gibt true zurück wenn die Form Bildbytes enthält oder ein Bild verknüpft.
type: docs
weight: 110
url: /de/net/aspose.words.drawing/imagedata/hasimage/
---
## ImageData.HasImage property

Gibt „true“ zurück, wenn die Form Bildbytes enthält oder ein Bild verknüpft.

```csharp
public bool HasImage { get; }
```

### Beispiele

Zeigt, wie alle Bilder eines Dokuments im Dateisystem gespeichert werden.

```csharp
Document imgSourceDoc = new Document(MyDir + "Images.docx");

// Shapes mit gesetztem "HasImage"-Flag speichern und zeigen alle Bilder des Dokuments an.
IEnumerable<Shape> shapesWithImages = 
    imgSourceDoc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Where(s => s.HasImage);

// Gehe durch jede Form und speichere ihr Bild.
ImageFormatConverter formatConverter = new ImageFormatConverter();

using (IEnumerator<Shape> enumerator = shapesWithImages.GetEnumerator())
{
    int shapeIndex = 0;

    while (enumerator.MoveNext())
    {
        ImageData imageData = enumerator.Current.ImageData;
        ImageFormat format = imageData.ToImage().RawFormat;
        string fileExtension = formatConverter.ConvertToString(format);

        using (FileStream fileStream = File.Create(ArtifactsDir + $"Drawing.SaveAllImages.{++shapeIndex}.{fileExtension}"))
            imageData.Save(fileStream);
    }
}
```

### Siehe auch

* class [ImageData](../)
* namensraum [Aspose.Words.Drawing](../../imagedata/)
* Montage [Aspose.Words](../../../)


