---
title: Enum ImlRenderingMode
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Saving.ImlRenderingMode opsomming. Gibt an wie InkObjekte InkML in feste Seitenformate gerendert werden.
type: docs
weight: 4990
url: /de/net/aspose.words.saving/imlrenderingmode/
---
## ImlRenderingMode enumeration

Gibt an, wie Ink-Objekte (InkML) in feste Seitenformate gerendert werden.

```csharp
public enum ImlRenderingMode
```

### Werte

| Name | Wert | Beschreibung |
| --- | --- | --- |
| Fallback | `0` | Wenn die Fallback-Form für das InkML-Objekt verfügbar ist, rendert Aspose.Words die Fallback-Form anstelle von InkML. |
| InkML | `1` | Aspose.Words ignoriert die Fallback-Form des InkML-Objekts (InkML) und rendert InkML selbst. Dies ist der Standardmodus. |

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

* namensraum [Aspose.Words.Saving](../../aspose.words.saving/)
* Montage [Aspose.Words](../../)


