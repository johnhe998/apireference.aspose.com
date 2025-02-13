---
title: HtmlSaveOptions.ResourceFolder
second_title: Aspose.Words för .NET API Referens
description: HtmlSaveOptions fast egendom. Anger en fysisk mapp där alla resurser som bilder typsnitt och extern CSS sparas när ett document exporteras till HTML. Standard är en tom sträng.
type: docs
weight: 420
url: /sv/net/aspose.words.saving/htmlsaveoptions/resourcefolder/
---
## HtmlSaveOptions.ResourceFolder property

Anger en fysisk mapp där alla resurser som bilder, typsnitt och extern CSS sparas när ett document exporteras till HTML. Standard är en tom sträng.

```csharp
public string ResourceFolder { get; set; }
```

### Anmärkningar

`ResourceFolder` är det enklaste sättet att ange en mapp där alla resurser ska skrivas. Ett annat sätt är att använda enskilda egenskaper[`FontsFolder`](../fontsfolder/) ,[`ImagesFolder`](../imagesfolder/) , och[`CssStyleSheetFileName`](../cssstylesheetfilename/).

`ResourceFolder` har lägre prioritet än mappar som anges via[`FontsFolder`](../fontsfolder/) , [`ImagesFolder`](../imagesfolder/) , och[`CssStyleSheetFileName`](../cssstylesheetfilename/) . Till exempel, om både `ResourceFolder` och[`FontsFolder`](../fontsfolder/)är specificerade, kommer teckensnitt att sparas till[`FontsFolder`](../fontsfolder/) , medan bilder och CSS kommer att sparas till`ResourceFolder`.

Om mappen som anges av`ResourceFolder` inte finns skapas den automatiskt.

### Exempel

Visar hur man ställer in mappar och mappalias för externt sparade resurser som Aspose.Words skapar när ett dokument sparas till HTML.

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
    ResourceFolderAlias = "http://example.com/resurser",
    ExportOriginalUrlForLinkedImages = true
};

doc.Save(ArtifactsDir + "HtmlSaveOptions.FolderAlias.html", options);
```

### Se även

* class [HtmlSaveOptions](../)
* namnutrymme [Aspose.Words.Saving](../../htmlsaveoptions/)
* hopsättning [Aspose.Words](../../../)


