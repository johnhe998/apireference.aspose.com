---
title: Enum WatermarkType
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.WatermarkType opsomming. Gibt den Wasserzeichentyp an.
type: docs
weight: 6380
url: /de/net/aspose.words/watermarktype/
---
## WatermarkType enumeration

Gibt den Wasserzeichentyp an.

```csharp
public enum WatermarkType
```

### Werte

| Name | Wert | Beschreibung |
| --- | --- | --- |
| Text | `0` | Gibt an, dass der Text als Wasserzeichen verwendet wird. |
| Image | `1` | Gibt an, dass das Bild als Wasserzeichen verwendet wird. |
| None | `2` | Zeigt an, dass kein Wasserzeichen gesetzt ist. |

### Beispiele

Zeigt, wie ein Textwasserzeichen erstellt wird.

```csharp
Document doc = new Document();

// Fügen Sie ein Nur-Text-Wasserzeichen hinzu.
doc.Watermark.SetText("Aspose Watermark");

// Wenn wir die Textformatierung als Wasserzeichen bearbeiten möchten,
// Wir können dies tun, indem wir beim Erstellen des Wasserzeichens ein TextWatermarkOptions-Objekt übergeben.
TextWatermarkOptions textWatermarkOptions = new TextWatermarkOptions();
textWatermarkOptions.FontFamily = "Arial";
textWatermarkOptions.FontSize = 36;
textWatermarkOptions.Color = Color.Black;
textWatermarkOptions.Layout = WatermarkLayout.Diagonal;
textWatermarkOptions.IsSemitrasparent = false;

doc.Watermark.SetText("Aspose Watermark", textWatermarkOptions);

doc.Save(ArtifactsDir + "Document.TextWatermark.docx");

// Wir können ein Wasserzeichen aus einem Dokument wie diesem entfernen.
if (doc.Watermark.Type == WatermarkType.Text)
    doc.Watermark.Remove();
```

### Siehe auch

* namensraum [Aspose.Words](../../aspose.words/)
* Montage [Aspose.Words](../../)


