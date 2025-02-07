---
title: ImageData.Save
second_title: Aspose.Words för .NET API Referens
description: ImageData metod. Sparar bilden i den angivna strömmen.
type: docs
weight: 190
url: /sv/net/aspose.words.drawing/imagedata/save/
---
## Save(Stream) {#save}

Sparar bilden i den angivna strömmen.

```csharp
public void Save(Stream stream)
```

| Parameter | Typ | Beskrivning |
| --- | --- | --- |
| stream | Stream | Streamen där bilden ska sparas. |

### Anmärkningar

Är det uppringarens ansvar att kassera strömobjektet.

### Exempel

Visar hur man sparar alla bilder från ett dokument till filsystemet.

```csharp
Document imgSourceDoc = new Document(MyDir + "Images.docx");

// Former med flaggan "HasImage" lagrar och visar alla dokumentets bilder.
IEnumerable<Shape> shapesWithImages = 
    imgSourceDoc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Where(s => s.HasImage);

// Gå igenom varje form och spara dess bild.
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

### Se även

* class [ImageData](../)
* namnutrymme [Aspose.Words.Drawing](../../imagedata/)
* hopsättning [Aspose.Words](../../../)

---

## Save(string) {#save_1}

Sparar bilden i en fil.

```csharp
public void Save(string fileName)
```

| Parameter | Typ | Beskrivning |
| --- | --- | --- |
| fileName | String | Filnamnet där bilden ska sparas. |

### Exempel

Visar hur man extraherar bilder från ett dokument och sparar dem i det lokala filsystemet som enskilda filer.

```csharp
Document doc = new Document(MyDir + "Images.docx");

// Hämta samlingen av former från dokumentet,
// och spara bilddata för varje form med en bild som en fil till det lokala filsystemet.
NodeCollection shapes = doc.GetChildNodes(NodeType.Shape, true);

Assert.AreEqual(9, shapes.Count(s => ((Shape)s).HasImage));

int imageIndex = 0;
foreach (Shape shape in shapes.OfType<Shape>())
{
    if (shape.HasImage)
    {
        // Bilddata för former kan innehålla bilder av många möjliga bildformat. 
        // Vi kan bestämma en filtillägg för varje bild automatiskt, baserat på dess format.
        string imageFileName =
            $"File.ExtractImages.{imageIndex}{FileFormatUtil.ImageTypeToExtension(shape.ImageData.ImageType)}";
        shape.ImageData.Save(ArtifactsDir + imageFileName);
        imageIndex++;
    }
}
```

### Se även

* class [ImageData](../)
* namnutrymme [Aspose.Words.Drawing](../../imagedata/)
* hopsättning [Aspose.Words](../../../)


