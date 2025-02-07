---
title: XamlFixedSaveOptions.ResourcesFolderAlias
second_title: Aspose.Words för .NET API Referens
description: XamlFixedSaveOptions fast egendom. Anger namnet på mappen som används för att konstruera bildURIer inskrivna i ett Xamldokument med fast sida. Standard ärnull .
type: docs
weight: 40
url: /sv/net/aspose.words.saving/xamlfixedsaveoptions/resourcesfolderalias/
---
## XamlFixedSaveOptions.ResourcesFolderAlias property

Anger namnet på mappen som används för att konstruera bild-URI:er inskrivna i ett Xaml-dokument med fast sida. Standard är`null` .

```csharp
public string ResourcesFolderAlias { get; set; }
```

### Anmärkningar

När du sparar en[`Document`](../../../aspose.words/document/) i Xaml-format med fast sida måste Aspose.Words spara alla -bilder som är inbäddade i dokumentet som fristående filer.[`ResourcesFolder`](../resourcesfolder/) låter dig ange var bilderna ska sparas och`ResourcesFolderAlias` tillåter att specificera hur bildens URI:er kommer att konstrueras.

### Exempel

Visar hur man skriver ut URI:erna för länkade resurser som skapats när ett dokument konverteras till .xaml i fast form.

```csharp
public void ResourceFolder()
{
    Document doc = new Document(MyDir + "Rendering.docx");
    ResourceUriPrinter callback = new ResourceUriPrinter();

    // Skapa ett "XamlFixedSaveOptions"-objekt, som vi kan skicka till dokumentets "Spara"-metod
    // för att ändra hur vi sparar dokumentet till XAML-sparformatet.
    XamlFixedSaveOptions options = new XamlFixedSaveOptions();

    Assert.AreEqual(SaveFormat.XamlFixed, options.SaveFormat);

    // Använd egenskapen "ResourcesFolder" för att tilldela en mapp i det lokala filsystemet som
    // Aspose.Words kommer att spara alla dokumentets länkade resurser, såsom bilder och typsnitt.
    options.ResourcesFolder = ArtifactsDir + "XamlFixedResourceFolder";

    // Använd egenskapen "ResourcesFolderAlias" för att använda den här mappen
    // när man konstruerar bild-URI:er istället för resursmappens namn.
    options.ResourcesFolderAlias = ArtifactsDir + "XamlFixedFolderAlias";

    options.ResourceSavingCallback = callback;

    // En mapp specificerad av "ResourcesFolderAlias" kommer att behöva innehålla resurserna istället för "ResourcesFolder".
    // Vi måste se till att mappen finns innan återuppringningens strömmar kan lägga sina resurser i den.
    Directory.CreateDirectory(options.ResourcesFolderAlias);

    doc.Save(ArtifactsDir + "XamlFixedSaveOptions.ResourceFolder.xaml", options);

    foreach (string resource in callback.Resources)
        Console.WriteLine(resource);
}

/// <summary>
/// Räknar och skriver ut URI:er för resurser som skapats under konvertering till fast .xaml.
/// </summary>
private class ResourceUriPrinter : IResourceSavingCallback
{
    public ResourceUriPrinter()
    {
        Resources = new List<string>();
    }

    void IResourceSavingCallback.ResourceSaving(ResourceSavingArgs args)
    {
        Resources.Add($"Resource \"{args.ResourceFileName}\"\n\t{args.ResourceFileUri}");

        // Om vi angav ett resursmappalias skulle vi också behöva
        // för att omdirigera varje ström för att placera dess resurs i aliasmappen.
        args.ResourceStream = new FileStream(args.ResourceFileUri, FileMode.Create);
        args.KeepResourceStreamOpen = false;
    }

    public List<string> Resources { get; }
}
```

### Se även

* class [XamlFixedSaveOptions](../)
* namnutrymme [Aspose.Words.Saving](../../xamlfixedsaveoptions/)
* hopsättning [Aspose.Words](../../../)


