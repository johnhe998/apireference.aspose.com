---
title: ImageData.HasImage
second_title: Aspose.Words för .NET API Referens
description: ImageData fast egendom. Returnerar sant om formen har bildbytes eller länkar en bild.
type: docs
weight: 110
url: /sv/net/aspose.words.drawing/imagedata/hasimage/
---
## ImageData.HasImage property

Returnerar sant om formen har bildbytes eller länkar en bild.

```csharp
public bool HasImage { get; }
```

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


