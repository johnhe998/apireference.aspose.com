---
title: XamlFlowSaveOptions.ImagesFolder
second_title: Aspose.Words för .NET API Referens
description: XamlFlowSaveOptions fast egendom. Anger den fysiska mappen där bilder sparas vid export av ett dokument till XAMLformat. Standard är en tom sträng.
type: docs
weight: 30
url: /sv/net/aspose.words.saving/xamlflowsaveoptions/imagesfolder/
---
## XamlFlowSaveOptions.ImagesFolder property

Anger den fysiska mappen där bilder sparas vid export av ett dokument till XAML-format. Standard är en tom sträng.

```csharp
public string ImagesFolder { get; set; }
```

### Anmärkningar

När du sparar en[`Document`](../../../aspose.words/document/) i XAML-format måste Aspose.Words spara alla -bilder som är inbäddade i dokumentet som fristående filer.`ImagesFolder` låter dig ange var bilderna ska sparas och[`ImagesFolderAlias`](../imagesfolderalias/) tillåter att specificera hur bildens URI:er kommer att konstrueras.

Om du sparar ett dokument i en fil och anger ett filnamn, sparar Aspose.Words, som standard, -bilderna i samma mapp där dokumentfilen sparas. Använda sig av`ImagesFolder` för att åsidosätta detta beteende.

Om du sparar ett dokument i en ström så har Aspose.Words ingen mapp där bilderna ska sparas, men behöver ändå spara bilderna någonstans. I det här fallet måste du ange en tillgänglig mapp i`ImagesFolder` egendom eller tillhandahålla anpassade strömmar via the[`ImageSavingCallback`](../imagesavingcallback/) händelsehanterare.

### Exempel

Visar hur man skriver ut filnamnen på länkade bilder som skapats när ett dokument konverteras till flödesformat .xaml.

```csharp
{
    Document doc = new Document(MyDir + "Rendering.docx");

    ImageUriPrinter callback = new ImageUriPrinter(ArtifactsDir + "XamlFlowImageFolderAlias");

    // Skapa ett "XamlFlowSaveOptions"-objekt, som vi kan skicka till dokumentets "Spara"-metod
    // för att ändra hur vi sparar dokumentet till XAML-sparformatet.
    XamlFlowSaveOptions options = new XamlFlowSaveOptions();

    Assert.AreEqual(SaveFormat.XamlFlow, options.SaveFormat);

    // Använd egenskapen "ImagesFolder" för att tilldela en mapp i det lokala filsystemet som
    // Aspose.Words kommer att spara alla dokumentets länkade bilder.
    options.ImagesFolder = ArtifactsDir + "XamlFlowImageFolder";

    // Använd egenskapen "ImagesFolderAlias" för att använda den här mappen
    // när du konstruerar bild-URI:er istället för bildmappens namn.
    options.ImagesFolderAlias = ArtifactsDir + "XamlFlowImageFolderAlias";

    options.ImageSavingCallback = callback;

    // En mapp specificerad av "ImagesFolderAlias" kommer att behöva innehålla resurserna istället för "ImagesFolder".
    // Vi måste se till att mappen finns innan återuppringningens strömmar kan lägga sina resurser i den.
    Directory.CreateDirectory(options.ImagesFolderAlias);

    doc.Save(ArtifactsDir + "XamlFlowSaveOptions.ImageFolder.xaml", options);

    foreach (string resource in callback.Resources)
        Console.WriteLine($"{callback.ImagesFolderAlias}/{resource}");

/// <summary>
/// Räknar och skriver ut filnamn på bilder medan deras överordnade dokument konverteras till flödesformen .xaml.
/// </summary>
private class ImageUriPrinter : IImageSavingCallback
{
    public ImageUriPrinter(string imagesFolderAlias)
    {
        ImagesFolderAlias = imagesFolderAlias;
        Resources = new List<string>();
    }

    void IImageSavingCallback.ImageSaving(ImageSavingArgs args)
    {
        Resources.Add(args.ImageFileName);

        // Om vi angav ett bildmappalias skulle vi också behöva
        // för att omdirigera varje ström för att placera dess bild i aliasmappen.
        args.ImageStream = new FileStream($"{ImagesFolderAlias}/{args.ImageFileName}", FileMode.Create);
        args.KeepImageStreamOpen = false;
    }

    public string ImagesFolderAlias { get; }
    public List<string> Resources { get; }
}
```

### Se även

* class [XamlFlowSaveOptions](../)
* namnutrymme [Aspose.Words.Saving](../../xamlflowsaveoptions/)
* hopsättning [Aspose.Words](../../../)


