---
title: HtmlSaveOptions.ResourceFolderAlias
second_title: Aspose.Words für .NET-API-Referenz
description: HtmlSaveOptions eigendom. Gibt den Namen des Ordners an der verwendet wird um URIs aller Ressourcen zu erstellen die in ein HTMLDokument geschrieben werden. Standard ist eine leere Zeichenfolge.
type: docs
weight: 430
url: /de/net/aspose.words.saving/htmlsaveoptions/resourcefolderalias/
---
## HtmlSaveOptions.ResourceFolderAlias property

Gibt den Namen des Ordners an, der verwendet wird, um URIs aller Ressourcen zu erstellen, die in ein HTML-Dokument geschrieben werden. Standard ist eine leere Zeichenfolge.

```csharp
public string ResourceFolderAlias { get; set; }
```

### Bemerkungen

`ResourceFolderAlias` ist der einfachste Weg, um anzugeben, wie URIs für alle Ressourcendateien aufgebaut sein sollen. Dieselben Informationen können für Bilder und Schriftarten getrennt über angegeben werden[`ImagesFolderAlias`](../imagesfolderalias/) und[`FontsFolderAlias`](../fontsfolderalias/) Eigenschaften bzw. Es gibt jedoch keine individuelle Eigenschaft für CSS.

`ResourceFolderAlias` hat eine niedrigere Priorität als[`FontsFolderAlias`](../fontsfolderalias/) und[`ImagesFolderAlias`](../imagesfolderalias/) . Wenn zum Beispiel beide`ResourceFolderAlias` und[`FontsFolderAlias`](../fontsfolderalias/) angegeben sind, werden die URIs der Schriftarten mit erstellt[`FontsFolderAlias`](../fontsfolderalias/) , während URIs von Bildern und CSS mit erstellt werden`ResourceFolderAlias`.

Wenn`ResourceFolderAlias` leer ist, die[`ResourceFolder`](../resourcefolder/)Eigenschaftswert wird used verwendet, um Ressourcen-URIs zu erstellen.

Wenn`ResourceFolderAlias` ist eingestellt auf '.' (Punkt), Ressourcen-URIs enthalten nur Dateinamen, ohne irgendeinen Pfad.

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


