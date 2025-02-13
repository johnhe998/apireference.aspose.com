---
title: XamlFlowSaveOptions.ImagesFolderAlias
second_title: Aspose.Words für .NET-API-Referenz
description: XamlFlowSaveOptions eigendom. Gibt den Namen des Ordners an der zum Erstellen von BildURIs verwendet wird die in ein XAMLDokument geschrieben werden. Standard ist eine leere Zeichenfolge.
type: docs
weight: 40
url: /de/net/aspose.words.saving/xamlflowsaveoptions/imagesfolderalias/
---
## XamlFlowSaveOptions.ImagesFolderAlias property

Gibt den Namen des Ordners an, der zum Erstellen von Bild-URIs verwendet wird, die in ein XAML-Dokument geschrieben werden. Standard ist eine leere Zeichenfolge.

```csharp
public string ImagesFolderAlias { get; set; }
```

### Bemerkungen

Beim Speichern von a[`Document`](../../../aspose.words/document/) im XAML-Format muss Aspose.Words alle in das Dokument eingebetteten -Bilder als eigenständige Dateien speichern.[`ImagesFolder`](../imagesfolder/) Mit können Sie angeben, wo die Bilder gespeichert werden und`ImagesFolderAlias` ermöglicht die Angabe, wie die Bild-URIs aufgebaut werden.

Wenn`ImagesFolderAlias` kein leerer String ist, dann wird der Bild-URI in XAML geschriebenImagesFolderAlias + &lt;Bilddateiname&gt;.

Wenn`ImagesFolderAlias` ein leerer String ist, dann wird der Bild-URI in XAML geschriebenImagesFolder + &lt;Name der Bilddatei&gt;.

Wenn`ImagesFolderAlias` ist eingestellt auf '.' (Punkt), dann wird der Bilddateiname unabhängig von anderen Optionen ohne Pfad in XAML geschrieben.

### Beispiele

Zeigt, wie die Dateinamen von verknüpften Bildern gedruckt werden, die beim Konvertieren eines Dokuments in Flow-Form-XAML-Dateien erstellt wurden.

```csharp
{
    Document doc = new Document(MyDir + "Rendering.docx");

    ImageUriPrinter callback = new ImageUriPrinter(ArtifactsDir + "XamlFlowImageFolderAlias");

    // Erstellen Sie ein „XamlFlowSaveOptions“-Objekt, das wir an die „Save“-Methode des Dokuments übergeben können
    // um zu ändern, wie wir das Dokument im XAML-Speicherformat speichern.
    XamlFlowSaveOptions options = new XamlFlowSaveOptions();

    Assert.AreEqual(SaveFormat.XamlFlow, options.SaveFormat);

    // Verwenden Sie die Eigenschaft "ImagesFolder", um einen Ordner im lokalen Dateisystem zuzuweisen, in den
    // Aspose.Words speichert alle verknüpften Bilder des Dokuments.
    options.ImagesFolder = ArtifactsDir + "XamlFlowImageFolder";

    // Verwenden Sie die Eigenschaft "ImagesFolderAlias", um diesen Ordner zu verwenden
    // beim Erstellen von Bild-URIs anstelle des Namens des Bildordners.
    options.ImagesFolderAlias = ArtifactsDir + "XamlFlowImageFolderAlias";

    options.ImageSavingCallback = callback;

    // Ein durch "ImagesFolderAlias" angegebener Ordner muss die Ressourcen anstelle von "ImagesFolder" enthalten.
    // Wir müssen sicherstellen, dass der Ordner existiert, bevor die Streams des Callbacks ihre Ressourcen darin ablegen können.
    Directory.CreateDirectory(options.ImagesFolderAlias);

    doc.Save(ArtifactsDir + "XamlFlowSaveOptions.ImageFolder.xaml", options);

    foreach (string resource in callback.Resources)
        Console.WriteLine($"{callback.ImagesFolderAlias}/{resource}");

/// <summary>
/// Zählt und druckt Dateinamen von Bildern, während ihr übergeordnetes Dokument in Flow-Form .xaml konvertiert wird.
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

        // Wenn wir einen Bildordner-Alias angeben, benötigen wir auch
        // Um jeden Stream umzuleiten, um sein Bild in den Alias-Ordner zu legen.
        args.ImageStream = new FileStream($"{ImagesFolderAlias}/{args.ImageFileName}", FileMode.Create);
        args.KeepImageStreamOpen = false;
    }

    public string ImagesFolderAlias { get; }
    public List<string> Resources { get; }
}
```

### Siehe auch

* class [XamlFlowSaveOptions](../)
* namensraum [Aspose.Words.Saving](../../xamlflowsaveoptions/)
* Montage [Aspose.Words](../../../)


