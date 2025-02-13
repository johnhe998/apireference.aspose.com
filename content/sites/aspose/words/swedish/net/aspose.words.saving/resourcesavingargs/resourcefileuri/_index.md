---
title: ResourceSavingArgs.ResourceFileUri
second_title: Aspose.Words för .NET API Referens
description: ResourceSavingArgs fast egendom. Hämtar eller ställer in den enhetliga resursidentifieraren URI som används för att referera till resursfilen från dokumentet.
type: docs
weight: 40
url: /sv/net/aspose.words.saving/resourcesavingargs/resourcefileuri/
---
## ResourceSavingArgs.ResourceFileUri property

Hämtar eller ställer in den enhetliga resursidentifieraren (URI) som används för att referera till resursfilen från dokumentet.

```csharp
public string ResourceFileUri { get; set; }
```

### Anmärkningar

Den här egenskapen låter dig ändra URI:er för resursfiler som exporteras till HTML- eller SVG-dokument med fasta sidor.

Aspose.Words genererar automatiskt en URI för varje resursfil under export till fast HTML eller SVG-format. De genererade URI:erna refererar till resursfiler som sparats av Aspose.Words. URI:erna kan dock vara felaktiga om resursfiler ska flyttas till en annan plats eller om resursfiler sparas i strömmar. Den här egenskapen gör det möjligt att korrigera URI:er i dessa fall.

När händelsen aktiveras innehåller den här egenskapen URI:n som genererades av Aspose.Words. Du kan ändra värdet på den här egenskapen för att tillhandahålla en anpassad URI för resursfilen.

[`ResourcesFolder`](../../htmlfixedsaveoptions/resourcesfolder/)[`ResourcesFolder`](../../svgsaveoptions/resourcesfolder/)[`ResourcesFolderAlias`](../../htmlfixedsaveoptions/resourcesfolderalias/)[`ResourcesFolderAlias`](../../svgsaveoptions/resourcesfolderalias/)

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

* class [ResourceSavingArgs](../)
* namnutrymme [Aspose.Words.Saving](../../resourcesavingargs/)
* hopsättning [Aspose.Words](../../../)


