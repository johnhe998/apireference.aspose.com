---
title: XamlFixedSaveOptions.ResourceSavingCallback
second_title: Aspose.Words för .NET API Referens
description: XamlFixedSaveOptions fast egendom. Gör det möjligt att styra hur resurser bilder och teckensnitt sparas när ett dokument exporteras till fast sidformat Xaml.
type: docs
weight: 20
url: /sv/net/aspose.words.saving/xamlfixedsaveoptions/resourcesavingcallback/
---
## XamlFixedSaveOptions.ResourceSavingCallback property

Gör det möjligt att styra hur resurser (bilder och teckensnitt) sparas när ett dokument exporteras till fast sidformat Xaml.

```csharp
public IResourceSavingCallback ResourceSavingCallback { get; set; }
```

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

* interface [IResourceSavingCallback](../../iresourcesavingcallback/)
* class [XamlFixedSaveOptions](../)
* namnutrymme [Aspose.Words.Saving](../../xamlfixedsaveoptions/)
* hopsättning [Aspose.Words](../../../)


