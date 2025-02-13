---
title: ResourceSavingArgs.ResourceFileName
second_title: Aspose.Words för .NET API Referens
description: ResourceSavingArgs fast egendom. Hämtar eller ställer in filnamnet utan sökväg där resursen ska sparas.
type: docs
weight: 30
url: /sv/net/aspose.words.saving/resourcesavingargs/resourcefilename/
---
## ResourceSavingArgs.ResourceFileName property

Hämtar eller ställer in filnamnet (utan sökväg) där resursen ska sparas.

```csharp
public string ResourceFileName { get; set; }
```

### Anmärkningar

Den här egenskapen låter dig omdefiniera hur resursfilnamnen genereras under export till fixerad HTML eller SVG.

När händelsen aktiveras innehåller den här egenskapen filnamnet som genererades av Aspose.Words. Du kan ändra värdet på den här egenskapen för att spara resursen i en annan fil. Observera att filnamn måste vara unika.

Aspose.Words genererar automatiskt ett unikt filnamn för varje resurs när exporteras till fast HTML- eller SVG-format. Hur resursfilnamnet genereras beror på om du sparar dokumentet i en fil eller i en ström.

När du sparar ett dokument till en fil ser det genererade resursfilnamnet ut som &lt;dokumentbasfilnamn&gt;.&lt;bildnummer&gt;.&lt;tillägg&gt;.

När du sparar ett dokument i en ström ser det genererade resursfilnamnet ut som Aspose.Words.&lt;dokumentguide&gt;.&lt;bildnummer&gt;.&lt;tillägg&gt;.

`ResourceFileName` måste endast innehålla filnamnet utan sökvägen. Aspose.Words bestämmer sökvägen för att spara och värdet på`src` attribut för att skriva till fast sida HTML eller SVG med hjälp av dokumentfilens namn, the[`ResourcesFolder`](../../htmlfixedsaveoptions/resourcesfolder/) eller[`ResourcesFolder`](../../svgsaveoptions/resourcesfolder/) och[`ResourcesFolderAlias`](../../htmlfixedsaveoptions/resourcesfolderalias/) eller[`ResourcesFolderAlias`](../../svgsaveoptions/resourcesfolderalias/) egenskaper.

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


