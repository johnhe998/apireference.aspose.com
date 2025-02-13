---
title: Document.UpdateThumbnail
second_title: Aspose.Words för .NET API Referens
description: Document metod. UppdateringarThumbnail av dokumentet enligt de angivna alternativen.
type: docs
weight: 760
url: /sv/net/aspose.words/document/updatethumbnail/
---
## UpdateThumbnail(ThumbnailGeneratingOptions) {#updatethumbnail_1}

Uppdateringar[`Thumbnail`](../../../aspose.words.properties/builtindocumentproperties/thumbnail/) av dokumentet enligt de angivna alternativen.

```csharp
public void UpdateThumbnail(ThumbnailGeneratingOptions options)
```

| Parameter | Typ | Beskrivning |
| --- | --- | --- |
| options | ThumbnailGeneratingOptions | Genereringsalternativen att använda. |

### Anmärkningar

Den[`ThumbnailGeneratingOptions`](../../../aspose.words.rendering/thumbnailgeneratingoptions/) låter dig ange källan till miniatyrbilden, storlek och andra alternativ. Om försöket att generera miniatyrer misslyckas, ändras inte en.

### Exempel

Visar hur man uppdaterar ett dokuments miniatyrbild.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Hello world!");
builder.InsertImage(ImageDir + "Logo.jpg");

// Det finns två sätt att ställa in en miniatyrbild när du sparar ett dokument i .epub.
// 1 - Använd dokumentets första sida:
doc.UpdateThumbnail();
doc.Save(ArtifactsDir + "Document.UpdateThumbnail.FirstPage.epub");

// 2 - Använd den första bilden som finns i dokumentet:
ThumbnailGeneratingOptions options = new ThumbnailGeneratingOptions();
options.ThumbnailSize = new Size(400, 400);
options.GenerateFromFirstPage = false;

doc.UpdateThumbnail(options);
doc.Save(ArtifactsDir + "Document.UpdateThumbnail.FirstImage.epub");
```

### Se även

* class [ThumbnailGeneratingOptions](../../../aspose.words.rendering/thumbnailgeneratingoptions/)
* class [Document](../)
* namnutrymme [Aspose.Words](../../document/)
* hopsättning [Aspose.Words](../../../)

---

## UpdateThumbnail() {#updatethumbnail}

Uppdateringar[`Thumbnail`](../../../aspose.words.properties/builtindocumentproperties/thumbnail/) av dokumentet med standardalternativ.

```csharp
public void UpdateThumbnail()
```

### Exempel

Visar hur man uppdaterar ett dokuments miniatyrbild.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Hello world!");
builder.InsertImage(ImageDir + "Logo.jpg");

// Det finns två sätt att ställa in en miniatyrbild när du sparar ett dokument i .epub.
// 1 - Använd dokumentets första sida:
doc.UpdateThumbnail();
doc.Save(ArtifactsDir + "Document.UpdateThumbnail.FirstPage.epub");

// 2 - Använd den första bilden som finns i dokumentet:
ThumbnailGeneratingOptions options = new ThumbnailGeneratingOptions();
options.ThumbnailSize = new Size(400, 400);
options.GenerateFromFirstPage = false;

doc.UpdateThumbnail(options);
doc.Save(ArtifactsDir + "Document.UpdateThumbnail.FirstImage.epub");
```

### Se även

* class [Document](../)
* namnutrymme [Aspose.Words](../../document/)
* hopsättning [Aspose.Words](../../../)


