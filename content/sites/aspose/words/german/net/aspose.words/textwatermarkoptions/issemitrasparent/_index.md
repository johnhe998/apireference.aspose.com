---
title: TextWatermarkOptions.IsSemitrasparent
second_title: Aspose.Words für .NET-API-Referenz
description: TextWatermarkOptions eigendom. Erhält oder setzt einen booleschen Wert der für die Deckkraft des Wasserzeichens verantwortlich ist. Der Standardwert ist True.
type: docs
weight: 50
url: /de/net/aspose.words/textwatermarkoptions/issemitrasparent/
---
## TextWatermarkOptions.IsSemitrasparent property

Erhält oder setzt einen booleschen Wert, der für die Deckkraft des Wasserzeichens verantwortlich ist. Der Standardwert ist True.

```csharp
public bool IsSemitrasparent { get; set; }
```

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

* class [TextWatermarkOptions](../)
* namensraum [Aspose.Words](../../textwatermarkoptions/)
* Montage [Aspose.Words](../../../)


