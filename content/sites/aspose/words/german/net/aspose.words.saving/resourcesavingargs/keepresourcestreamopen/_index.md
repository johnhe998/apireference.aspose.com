---
title: ResourceSavingArgs.KeepResourceStreamOpen
second_title: Aspose.Words für .NET-API-Referenz
description: ResourceSavingArgs eigendom. Gibt an ob Aspose.Words den Stream offen halten oder nach dem Speichern einer Ressource schließen soll.
type: docs
weight: 20
url: /de/net/aspose.words.saving/resourcesavingargs/keepresourcestreamopen/
---
## ResourceSavingArgs.KeepResourceStreamOpen property

Gibt an, ob Aspose.Words den Stream offen halten oder nach dem Speichern einer Ressource schließen soll.

```csharp
public bool KeepResourceStreamOpen { get; set; }
```

### Bemerkungen

Standard ist`FALSCH` und Aspose.Words schließt den von Ihnen bereitgestellten Stream in der[`ResourceStream`](../resourcestream/) Eigenschaft, nachdem eine Ressource hineingeschrieben wurde. Angeben`Stimmt` um den Strom offen zu halten.

### Beispiele

Zeigt, wie ein Rückruf verwendet wird, um die URIs externer Ressourcen zu drucken, die beim Konvertieren eines Dokuments in HTML erstellt wurden.

```csharp
public void HtmlFixedResourceFolder()
{
    Document doc = new Document(MyDir + "Rendering.docx");

    ResourceUriPrinter callback = new ResourceUriPrinter();

    HtmlFixedSaveOptions options = new HtmlFixedSaveOptions
    {
        SaveFormat = SaveFormat.HtmlFixed,
        ExportEmbeddedImages = false,
        ResourcesFolder = ArtifactsDir + "HtmlFixedResourceFolder",
        ResourcesFolderAlias = ArtifactsDir + "HtmlFixedResourceFolderAlias",
        ShowPageBorder = false,
        ResourceSavingCallback = callback
    };

    // Ein durch ResourcesFolderAlias angegebener Ordner enthält die Ressourcen anstelle von ResourcesFolder.
    // Wir müssen sicherstellen, dass der Ordner existiert, bevor die Streams ihre Ressourcen darin ablegen können.
    Directory.CreateDirectory(options.ResourcesFolderAlias);

    doc.Save(ArtifactsDir + "HtmlFixedSaveOptions.HtmlFixedResourceFolder.html", options);

    Console.WriteLine(callback.GetText());

    string[] resourceFiles = Directory.GetFiles(ArtifactsDir + "HtmlFixedResourceFolderAlias");

    Assert.False(Directory.Exists(ArtifactsDir + "HtmlFixedResourceFolder"));
    Assert.AreEqual(6, resourceFiles.Count(f => f.EndsWith(".jpeg") || f.EndsWith(".png") || f.EndsWith(".css")));
}

/// <summary>
/// Zählt und druckt URIs von Ressourcen, die in enthalten sind, während sie in festes HTML konvertiert werden.
/// </summary>
private class ResourceUriPrinter : IResourceSavingCallback
{
    void IResourceSavingCallback.ResourceSaving(ResourceSavingArgs args)
    {
        // Wenn wir im SaveOptions-Objekt einen Ordner-Alias festlegen, können wir ihn von hier aus drucken.
        mText.AppendLine($"Resource #{++mSavedResourceCount} \"{args.ResourceFileName}\"");

        string extension = Path.GetExtension(args.ResourceFileName);
        switch (extension)
        {
            case ".ttf":
            case ".woff":
            {
                // Standardmäßig verwendet 'ResourceFileUri' den Systemordner für Schriftarten.
                // Um Probleme auf anderen Plattformen zu vermeiden, müssen Sie den Pfad für die Schriftarten explizit angeben.
                args.ResourceFileUri = ArtifactsDir + Path.DirectorySeparatorChar + args.ResourceFileName;
                break;
            }
        }

        mText.AppendLine("\t" + args.ResourceFileUri);

        // Wenn wir in der Eigenschaft "ResourcesFolderAlias" einen Ordner angegeben haben,
        // Wir müssen auch jeden Stream umleiten, um seine Ressource in diesen Ordner zu legen.
        args.ResourceStream = new FileStream(args.ResourceFileUri, FileMode.Create);
        args.KeepResourceStreamOpen = false;
    }

    public string GetText()
    {
        return mText.ToString();
    }

    private int mSavedResourceCount;
    private readonly StringBuilder mText = new StringBuilder();
}
```

### Siehe auch

* class [ResourceSavingArgs](../)
* namensraum [Aspose.Words.Saving](../../resourcesavingargs/)
* Montage [Aspose.Words](../../../)


