---
title: ImageData.Save
linktitle: Save
articleTitle: Save
second_title: Aspose.Words for .NET
description: ImageData Save method. Saves the image into the specified stream in C#.
type: docs
weight: 190
url: /net/aspose.words.drawing/imagedata/save/
---
## Save(*Stream*) {#save}

Saves the image into the specified stream.

```csharp
public void Save(Stream stream)
```

| Parameter | Type | Description |
| --- | --- | --- |
| stream | Stream | The stream where to save the image to. |

## Remarks

Is it the responsibility of the caller to dispose the stream object.

## Examples

Shows how to save all images from a document to the file system.

```csharp
Document imgSourceDoc = new Document(MyDir + "Images.docx");

// Shapes with the "HasImage" flag set store and display all the document's images.
IEnumerable<Shape> shapesWithImages = 
    imgSourceDoc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Where(s => s.HasImage);

// Go through each shape and save its image.
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

### See Also

* class [ImageData](../)
* namespace [Aspose.Words.Drawing](../../../aspose.words.drawing/)
* assembly [Aspose.Words](../../../)

---

## Save(*string*) {#save_1}

Saves the image into a file.

```csharp
public void Save(string fileName)
```

| Parameter | Type | Description |
| --- | --- | --- |
| fileName | String | The file name where to save the image. |

## Examples

Shows how to extract images from a document, and save them to the local file system as individual files.

```csharp
Document doc = new Document(MyDir + "Images.docx");

// Get the collection of shapes from the document,
// and save the image data of every shape with an image as a file to the local file system.
NodeCollection shapes = doc.GetChildNodes(NodeType.Shape, true);

Assert.AreEqual(9, shapes.Count(s => ((Shape)s).HasImage));

int imageIndex = 0;
foreach (Shape shape in shapes.OfType<Shape>())
{
    if (shape.HasImage)
    {
        // The image data of shapes may contain images of many possible image formats. 
        // We can determine a file extension for each image automatically, based on its format.
        string imageFileName =
            $"File.ExtractImages.{imageIndex}{FileFormatUtil.ImageTypeToExtension(shape.ImageData.ImageType)}";
        shape.ImageData.Save(ArtifactsDir + imageFileName);
        imageIndex++;
    }
}
```

### See Also

* class [ImageData](../)
* namespace [Aspose.Words.Drawing](../../../aspose.words.drawing/)
* assembly [Aspose.Words](../../../)
