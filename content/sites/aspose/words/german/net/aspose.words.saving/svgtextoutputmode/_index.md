---
title: Enum SvgTextOutputMode
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Saving.SvgTextOutputMode opsomming. 
type: docs
weight: 5330
url: /de/net/aspose.words.saving/svgtextoutputmode/
---
## SvgTextOutputMode enumeration

```csharp
public enum SvgTextOutputMode
```

### Werte

| Name | Wert | Beschreibung |
| --- | --- | --- |
| UseSvgFonts | `0` | SVG-Schriftarten werden zum Rendern von Text verwendet. Beachten Sie, dass nicht alle Browser SVG-Schriftarten unterstützen. |
| UseTargetMachineFonts | `1` | Schriftarten, die auf dem Zielcomputer installiert sind, werden zum Rendern von Text verwendet. Hinweis: Wenn einige der im Dokument verwendeten Schriftarten auf dem Zielcomputer nicht verfügbar sind, kann das Dokument anders aussehen. |
| UsePlacedGlyphs | `2` | Text wird mit Kurven gerendert. Beachten Sie, dass die Textauswahl nicht funktioniert, wenn Sie diese Option verwenden. |

### Beispiele

Zeigt, wie die Eigenschaften von Bildern beim Konvertieren eines .docx-Dokuments in .svg nachgeahmt werden.

```csharp
Document doc = new Document(MyDir + "Document.docx");

// Konfigurieren Sie das SvgSaveOptions-Objekt so, dass es ohne Seitenränder oder auswählbaren Text gespeichert wird.
SvgSaveOptions options = new SvgSaveOptions
{
    FitToViewPort = true,
    ShowPageBorder = false,
    TextOutputMode = SvgTextOutputMode.UsePlacedGlyphs
};

doc.Save(ArtifactsDir + "SvgSaveOptions.SaveLikeImage.svg", options);
```

### Siehe auch

* namensraum [Aspose.Words.Saving](../../aspose.words.saving/)
* Montage [Aspose.Words](../../)


