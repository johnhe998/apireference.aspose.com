---
title: SaveOptions.ImlRenderingMode
second_title: Aspose.Words für .NET-API-Referenz
description: SaveOptions eigendom. Ruft einen Wert ab oder legt einen Wert fest der bestimmt wie InkObjekte InkML gerendert werden.
type: docs
weight: 100
url: /de/net/aspose.words.saving/saveoptions/imlrenderingmode/
---
## SaveOptions.ImlRenderingMode property

Ruft einen Wert ab oder legt einen Wert fest, der bestimmt, wie Ink-Objekte (InkML) gerendert werden.

```csharp
public ImlRenderingMode ImlRenderingMode { get; set; }
```

### Bemerkungen

Der Standardwert istInkML .

Diese Eigenschaft wird verwendet, wenn das Dokument in feste Seitenformate exportiert wird.

### Beispiele

Zeigt, wie Ink-Objekte gerendert werden.

```csharp
Document doc = new Document(MyDir + "Ink object.docx");

// Set 'ImlRenderingMode.InkML' ignoriert die Fallback-Form des Tintenobjekts (InkML) und rendert InkML selbst.
// Wenn das Rendering-Ergebnis unbefriedigend ist,
// Bitte verwenden Sie 'ImlRenderingMode.Fallback', um ein ähnliches Ergebnis wie in früheren Versionen zu erhalten.
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Jpeg)
{
    ImlRenderingMode = ImlRenderingMode.InkML
};

doc.Save(ArtifactsDir + "ImageSaveOptions.RenderInkObject.jpeg", saveOptions);
```

### Siehe auch

* enum [ImlRenderingMode](../../imlrenderingmode/)
* class [SaveOptions](../)
* namensraum [Aspose.Words.Saving](../../saveoptions/)
* Montage [Aspose.Words](../../../)


