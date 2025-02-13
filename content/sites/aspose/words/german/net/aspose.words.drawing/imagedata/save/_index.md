---
title: ImageData.Save
second_title: Aspose.Words für .NET-API-Referenz
description: ImageData methode. Speichert das Bild im angegebenen Stream.
type: docs
weight: 190
url: /de/net/aspose.words.drawing/imagedata/save/
---
## Save(Stream) {#save}

Speichert das Bild im angegebenen Stream.

```csharp
public void Save(Stream stream)
```

| Parameter | Typ | Beschreibung |
| --- | --- | --- |
| stream | Stream | Der Stream, in dem das Bild gespeichert werden soll. |

### Bemerkungen

Liegt es in der Verantwortung des Aufrufers, das Stream-Objekt zu entsorgen?

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

---

## Save(string) {#save_1}

Speichert das Bild in einer Datei.

```csharp
public void Save(string fileName)
```

| Parameter | Typ | Beschreibung |
| --- | --- | --- |
| fileName | String | Der Dateiname, unter dem das Bild gespeichert werden soll. |

### Beispiele

Zeigt, wie Bilder aus einem Dokument extrahiert und als einzelne Dateien im lokalen Dateisystem gespeichert werden.

```csharp
Document doc = new Document(MyDir + "Images.docx");

// Holen Sie sich die Sammlung von Formen aus dem Dokument,
// und die Bilddaten jeder Form mit einem Bild als Datei im lokalen Dateisystem speichern.
NodeCollection shapes = doc.GetChildNodes(NodeType.Shape, true);

Assert.AreEqual(9, shapes.Count(s => ((Shape)s).HasImage));

int imageIndex = 0;
foreach (Shape shape in shapes.OfType<Shape>())
{
    if (shape.HasImage)
    {
        // Die Bilddaten von Formen können Bilder in vielen möglichen Bildformaten enthalten. 
        // Wir können für jedes Bild automatisch eine Dateierweiterung basierend auf seinem Format bestimmen.
        string imageFileName =
            $"File.ExtractImages.{imageIndex}{FileFormatUtil.ImageTypeToExtension(shape.ImageData.ImageType)}";
        shape.ImageData.Save(ArtifactsDir + imageFileName);
        imageIndex++;
    }
}
```

### Siehe auch

* class [ImageData](../)
* namensraum [Aspose.Words.Drawing](../../imagedata/)
* Montage [Aspose.Words](../../../)


