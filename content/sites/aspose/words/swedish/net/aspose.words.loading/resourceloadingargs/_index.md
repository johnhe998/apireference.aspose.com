---
title: Class ResourceLoadingArgs
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.Loading.ResourceLoadingArgs klass. Tillhandahåller data förResourceLoading metod.
type: docs
weight: 3490
url: /sv/net/aspose.words.loading/resourceloadingargs/
---
## ResourceLoadingArgs class

Tillhandahåller data för[`ResourceLoading`](../iresourceloadingcallback/resourceloading/) metod.

```csharp
public class ResourceLoadingArgs
```

## Egenskaper

| namn | Beskrivning |
| --- | --- |
| [OriginalUri](../../aspose.words.loading/resourceloadingargs/originaluri/) { get; } | Ursprunglig URI för resursen som anges i importerat dokument. |
| [ResourceType](../../aspose.words.loading/resourceloadingargs/resourcetype/) { get; } | Typ av resurs. |
| [Uri](../../aspose.words.loading/resourceloadingargs/uri/) { get; set; } | URI för resursen som används för nedladdning if[`ResourceLoading`](../iresourceloadingcallback/resourceloading/) returnerarDefault. |

## Metoder

| namn | Beskrivning |
| --- | --- |
| [SetData](../../aspose.words.loading/resourceloadingargs/setdata/)(byte[]) | Anger data från användaren för resursen som används om[`ResourceLoading`](../iresourceloadingcallback/resourceloading/) returnerarUserProvided . |

### Exempel

Visar hur man anpassar processen för att ladda externa resurser i ett dokument.

```csharp
{
    Document doc = new Document();
    doc.ResourceLoadingCallback = new ImageNameHandler();

    DocumentBuilder builder = new DocumentBuilder(doc);

    // Bilder infogas vanligtvis med en URI eller en byte-array.
    // Varje instans av en resursladdning kommer att anropa vår callbacks ResourceLoading-metod.
    builder.InsertImage("Google logo");
    builder.InsertImage("Aspose logo");
    builder.InsertImage("Watermark");

    Assert.AreEqual(3, doc.GetChildNodes(NodeType.Shape, true).Count);

    doc.Save(ArtifactsDir + "DocumentBase.ResourceLoadingCallback.docx");

/// <summary>
/// Låter oss läsa in bilder i ett dokument med fördefinierade förkortningar, till skillnad från URI:er.
/// Detta kommer att separera logik för bildladdning från resten av dokumentkonstruktionen.
/// </summary>
private class ImageNameHandler : IResourceLoadingCallback
{
    public ResourceLoadingAction ResourceLoading(ResourceLoadingArgs args)
    {
        // Om denna återuppringning stöter på en av bildens förkortningar när en bild laddas,
        // det kommer att tillämpa unik logik för varje definierad stenografi istället för att behandla den som en URI.
        if (args.ResourceType == ResourceType.Image)
            switch (args.OriginalUri)
            {
                case "Google logo":
                    using (WebClient webClient = new WebClient())
                    {
                        args.SetData(webClient.DownloadData("http://www.google.com/images/logos/ps_logo2.png"));
                    }

                    return ResourceLoadingAction.UserProvided;

                case "Aspose logo":
                    args.SetData(File.ReadAllBytes(ImageDir + "Logo.jpg"));

                    return ResourceLoadingAction.UserProvided;

                case "Watermark":
                    args.SetData(File.ReadAllBytes(ImageDir + "Transparent background logo.png"));

                    return ResourceLoadingAction.UserProvided;
            }

        return ResourceLoadingAction.Default;
    }
}
```

### Se även

* namnutrymme [Aspose.Words.Loading](../../aspose.words.loading/)
* hopsättning [Aspose.Words](../../)


