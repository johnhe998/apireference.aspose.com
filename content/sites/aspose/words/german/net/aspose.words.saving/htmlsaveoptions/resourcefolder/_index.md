---
title: HtmlSaveOptions.ResourceFolder
second_title: Aspose.Words für .NET-API-Referenz
description: HtmlSaveOptions eigendom. Gibt einen physischen Ordner an in dem alle Ressourcen wie Bilder Schriftarten und externes CSS gespeichert werden wenn ein document in HTML exportiert wird. Standard ist eine leere Zeichenfolge.
type: docs
weight: 420
url: /de/net/aspose.words.saving/htmlsaveoptions/resourcefolder/
---
## HtmlSaveOptions.ResourceFolder property

Gibt einen physischen Ordner an, in dem alle Ressourcen wie Bilder, Schriftarten und externes CSS gespeichert werden, wenn ein document in HTML exportiert wird. Standard ist eine leere Zeichenfolge.

```csharp
public string ResourceFolder { get; set; }
```

### Bemerkungen

`ResourceFolder` ist die einfachste Möglichkeit, einen Ordner anzugeben, in den alle Ressourcen geschrieben werden sollen. Eine andere Möglichkeit besteht darin, einzelne Eigenschaften zu verwenden[`FontsFolder`](../fontsfolder/) ,[`ImagesFolder`](../imagesfolder/) , und[`CssStyleSheetFileName`](../cssstylesheetfilename/).

`ResourceFolder` hat eine niedrigere Priorität als die über angegebenen Ordner[`FontsFolder`](../fontsfolder/) , [`ImagesFolder`](../imagesfolder/) , und[`CssStyleSheetFileName`](../cssstylesheetfilename/) . Wenn beispielsweise both `ResourceFolder` und[`FontsFolder`](../fontsfolder/)angegeben sind, werden Schriften gespeichert in[`FontsFolder`](../fontsfolder/) , während Bilder und CSS gespeichert werden`ResourceFolder`.

Wenn der angegebene Ordner durch`ResourceFolder` existiert nicht, wird automatisch erstellt.

### Beispiele

Zeigt, wie Ordner und Ordneraliase für extern gespeicherte Ressourcen festgelegt werden, die Aspose.Words erstellt, wenn ein Dokument in HTML gespeichert wird.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

HtmlSaveOptions options = new HtmlSaveOptions
{
    CssStyleSheetType = CssStyleSheetType.External,
    ExportFontResources = true,
    ImageResolution = 72,
    FontResourcesSubsettingSizeThreshold = 0,
    FontsFolder = ArtifactsDir + "Fonts",
    ImagesFolder = ArtifactsDir + "Images",
    ResourceFolder = ArtifactsDir + "Resources",
    FontsFolderAlias = "http://example.com/fonts",
    ImagesFolderAlias = "http://example.com/images",
    ResourceFolderAlias = "http://example.com/resources",
    ExportOriginalUrlForLinkedImages = true
};

doc.Save(ArtifactsDir + "HtmlSaveOptions.FolderAlias.html", options);
```

### Siehe auch

* class [HtmlSaveOptions](../)
* namensraum [Aspose.Words.Saving](../../htmlsaveoptions/)
* Montage [Aspose.Words](../../../)


