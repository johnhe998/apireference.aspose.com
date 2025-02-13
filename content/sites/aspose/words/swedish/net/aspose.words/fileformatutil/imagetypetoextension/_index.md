---
title: FileFormatUtil.ImageTypeToExtension
second_title: Aspose.Words för .NET API Referens
description: FileFormatUtil metod. Konverterar ett uppräknat värde av bildtyp Aspose.Words till ett filtillägg. Det returnerade tillägget är en sträng med små bokstäver med en inledande punkt.
type: docs
weight: 50
url: /sv/net/aspose.words/fileformatutil/imagetypetoextension/
---
## FileFormatUtil.ImageTypeToExtension method

Konverterar ett uppräknat värde av bildtyp Aspose.Words till ett filtillägg. Det returnerade tillägget är en sträng med små bokstäver med en inledande punkt.

```csharp
public static string ImageTypeToExtension(ImageType imageType)
```

### Undantag

| undantag | skick |
| --- | --- |
| ArgumentException | Kastar när det inte går att konvertera. |

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

* enum [ImageType](../../../aspose.words.drawing/imagetype/)
* class [FileFormatUtil](../)
* namnutrymme [Aspose.Words](../../fileformatutil/)
* hopsättning [Aspose.Words](../../../)


