---
title: SvgSaveOptions.ExportEmbeddedImages
second_title: Aspose.Words für .NET-API-Referenz
description: SvgSaveOptions eigendom. Gibt an ob Bilder als Base64 in das SVGDokument eingebettet werden sollen. Beachten Sie dass das Setzen dieses Flags die Größe der ausgegebenen SVGDatei erheblich erhöhen kann.
type: docs
weight: 20
url: /de/net/aspose.words.saving/svgsaveoptions/exportembeddedimages/
---
## SvgSaveOptions.ExportEmbeddedImages property

Gibt an, ob Bilder als Base64 in das SVG-Dokument eingebettet werden sollen. Beachten Sie, dass das Setzen dieses Flags die Größe der ausgegebenen SVG-Datei erheblich erhöhen kann.

```csharp
public bool ExportEmbeddedImages { get; set; }
```

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


