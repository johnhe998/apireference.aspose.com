---
title: LoadOptions.BaseUri
second_title: Aspose.Words för .NET API Referens
description: LoadOptions fast egendom. Hämtar eller ställer in strängen som ska användas för att lösa relativa URIer som finns i dokumentet till absoluta URIer vid behov. Kan vara null eller tom sträng. Standard är null.
type: docs
weight: 20
url: /sv/net/aspose.words.loading/loadoptions/baseuri/
---
## LoadOptions.BaseUri property

Hämtar eller ställer in strängen som ska användas för att lösa relativa URI:er som finns i dokumentet till absoluta URI:er vid behov. Kan vara null eller tom sträng. Standard är null.

```csharp
public string BaseUri { get; set; }
```

### Anmärkningar

Den här egenskapen används för att lösa relativa URI:er till absoluta i följande fall:

1. När ett HTML-dokument laddas från en ström och dokumentet innehåller bilder med relativa URI:er och inte har en bas-URI specificerad i BASE HTML-elementet.
2. När du sparar ett dokument till PDF och andra format, för att hämta bilder länkade med relativa URIs så att bilderna kan sparas i utdatadokumentet.

### Exempel

Visar hur man öppnar ett HTML-dokument med bilder från en ström med en bas-URI.

```csharp
using (Stream stream = File.OpenRead(MyDir + "Document.html"))
{
    // Skicka URI:n för basmappen medan du laddar den
    // så att alla bilder med relativa URI:er i HTML-dokumentet kan hittas.
    LoadOptions loadOptions = new LoadOptions();
    loadOptions.BaseUri = ImageDir;

    Document doc = new Document(stream, loadOptions);

    // Verifiera att den första formen av dokumentet innehåller en giltig bild.
    Shape shape = (Shape)doc.GetChild(NodeType.Shape, 0, true);

    Assert.IsTrue(shape.IsImage);
    Assert.IsNotNull(shape.ImageData.ImageBytes);
    Assert.AreEqual(32.0, ConvertUtil.PointToPixel(shape.Width), 0.01);
    Assert.AreEqual(32.0, ConvertUtil.PointToPixel(shape.Height), 0.01);
}
```

### Se även

* class [LoadOptions](../)
* namnutrymme [Aspose.Words.Loading](../../loadoptions/)
* hopsättning [Aspose.Words](../../../)


