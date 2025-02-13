---
title: ImageData.HasImage
second_title: Aspose.Words per .NET API Reference
description: ImageData proprietà. Restituisce vero se la forma ha byte di immagine o collega unimmagine.
type: docs
weight: 110
url: /it/net/aspose.words.drawing/imagedata/hasimage/
---
## ImageData.HasImage property

Restituisce vero se la forma ha byte di immagine o collega un'immagine.

```csharp
public bool HasImage { get; }
```

### Esempi

Mostra come salvare tutte le immagini da un documento nel file system.

```csharp
Document imgSourceDoc = new Document(MyDir + "Images.docx");

// Le forme con il flag "HasImage" memorizzano e visualizzano tutte le immagini del documento.
IEnumerable<Shape> shapesWithImages = 
    imgSourceDoc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Where(s => s.HasImage);

// Scorri ogni forma e salva la sua immagine.
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

### Guarda anche

* class [ImageData](../)
* spazio dei nomi [Aspose.Words.Drawing](../../imagedata/)
* assemblea [Aspose.Words](../../../)


