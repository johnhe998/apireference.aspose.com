---
title: SvgSaveOptions.ResourcesFolderAlias
second_title: Aspose.Words für .NET-API-Referenz
description: SvgSaveOptions eigendom. Gibt den Namen des Ordners an der zum Erstellen von BildURIs verwendet wird die in ein SVGDokument geschrieben werden. Standard istNull .
type: docs
weight: 60
url: /de/net/aspose.words.saving/svgsaveoptions/resourcesfolderalias/
---
## SvgSaveOptions.ResourcesFolderAlias property

Gibt den Namen des Ordners an, der zum Erstellen von Bild-URIs verwendet wird, die in ein SVG-Dokument geschrieben werden. Standard ist`Null` .

```csharp
public string ResourcesFolderAlias { get; set; }
```

### Bemerkungen

Beim Speichern von a[`Document`](../../../aspose.words/document/)im SVG-Format muss Aspose.Words alle in das Dokument eingebetteten -Bilder als eigenständige Dateien speichern.[`ResourcesFolder`](../resourcesfolder/) Mit können Sie angeben, wo die Bilder gespeichert werden und`ResourcesFolderAlias` ermöglicht die Angabe, wie die Bild-URIs aufgebaut werden.

### Beispiele

Zeigt, wie die URIs verknüpfter Ressourcen bearbeitet und gedruckt werden, die beim Konvertieren eines Dokuments in .svg erstellt wurden.

```csharp
public void SvgResourceFolder()
{
    Document doc = new Document(MyDir + "Rendering.docx");

    SvgSaveOptions options = new SvgSaveOptions
    {
        SaveFormat = SaveFormat.Svg,
        ExportEmbeddedImages = false,
        ResourcesFolder = ArtifactsDir + "SvgResourceFolder",
        ResourcesFolderAlias = ArtifactsDir + "SvgResourceFolderAlias",
        ShowPageBorder = false,

        ResourceSavingCallback = new ResourceUriPrinter()
    };

    Directory.CreateDirectory(options.ResourcesFolderAlias);

    doc.Save(ArtifactsDir + "SvgSaveOptions.SvgResourceFolder.svg", options);
}

/// <summary>
/// Zählt und druckt URIs von Ressourcen, die in enthalten sind, während sie in .svg konvertiert werden.
/// </summary>
private class ResourceUriPrinter : IResourceSavingCallback
{
    void IResourceSavingCallback.ResourceSaving(ResourceSavingArgs args)
    {
        Console.WriteLine($"Resource #{++mSavedResourceCount} \"{args.ResourceFileName}\"");
        Console.WriteLine("\t" + args.ResourceFileUri);
    }

    private int mSavedResourceCount;
}
```

### Siehe auch

* class [SvgSaveOptions](../)
* namensraum [Aspose.Words.Saving](../../svgsaveoptions/)
* Montage [Aspose.Words](../../../)


