---
title: ResourceSavingArgs.Document
second_title: Aspose.Words för .NET API Referens
description: ResourceSavingArgs fast egendom. Hämtar dokumentobjektet som för närvarande sparas.
type: docs
weight: 10
url: /sv/net/aspose.words.saving/resourcesavingargs/document/
---
## ResourceSavingArgs.Document property

Hämtar dokumentobjektet som för närvarande sparas.

```csharp
public Document Document { get; }
```

### Exempel

Visar hur man använder en återuppringning för att spåra externa resurser som skapas när ett dokument konverteras till HTML.

```csharp
public void ResourceSavingCallback()
{
    Document doc = new Document(MyDir + "Bullet points with alternative font.docx");

    FontSavingCallback callback = new FontSavingCallback();

    HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions
    {
        ResourceSavingCallback = callback
    };

    doc.Save(ArtifactsDir + "HtmlFixedSaveOptions.UsingMachineFonts.html", saveOptions);

    Console.WriteLine(callback.GetText());
}

private class FontSavingCallback : IResourceSavingCallback
{
    /// <summary>
    /// Anropas när Aspose.Words sparar en extern resurs till fixerad HTML eller SVG.
    /// </summary>
    public void ResourceSaving(ResourceSavingArgs args)
    {
        mText.AppendLine($"Original document URI:\t{args.Document.OriginalFileName}");
        mText.AppendLine($"Resource being saved:\t{args.ResourceFileName}");
        mText.AppendLine($"Full uri after saving:\t{args.ResourceFileUri}\n");
    }

    public string GetText()
    {
        return mText.ToString();
    }

    private readonly StringBuilder mText = new StringBuilder();
}
```

### Se även

* class [Document](../../../aspose.words/document/)
* class [ResourceSavingArgs](../)
* namnutrymme [Aspose.Words.Saving](../../resourcesavingargs/)
* hopsättning [Aspose.Words](../../../)


