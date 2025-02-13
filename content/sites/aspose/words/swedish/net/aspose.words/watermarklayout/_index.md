---
title: Enum WatermarkLayout
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.WatermarkLayout uppräkning. Definierar layouten för vattenstämpeln i förhållande till vattenstämpelns centrum.
type: docs
weight: 6370
url: /sv/net/aspose.words/watermarklayout/
---
## WatermarkLayout enumeration

Definierar layouten för vattenstämpeln i förhållande till vattenstämpelns centrum.

```csharp
public enum WatermarkLayout
```

### Värderingar

| namn | Värde | Beskrivning |
| --- | --- | --- |
| Horizontal | `0` | Horisontell vattenstämpellayout. Motsvarar 0 graders rotation. |
| Diagonal | `315` | Diagonal vattenstämpellayout. Motsvarar 315 graders rotation. |

### Exempel

Visar hur man skapar en textvattenstämpel.

```csharp
Document doc = new Document();

// Lägg till en vanlig text vattenstämpel.
doc.Watermark.SetText("Aspose Watermark");

// Om vi vill redigera textformateringen med den som vattenstämpel,
// vi kan göra det genom att skicka ett TextWatermarkOptions-objekt när du skapar vattenstämpeln.
TextWatermarkOptions textWatermarkOptions = new TextWatermarkOptions();
textWatermarkOptions.FontFamily = "Arial";
textWatermarkOptions.FontSize = 36;
textWatermarkOptions.Color = Color.Black;
textWatermarkOptions.Layout = WatermarkLayout.Diagonal;
textWatermarkOptions.IsSemitrasparent = false;

doc.Watermark.SetText("Aspose Watermark", textWatermarkOptions);

doc.Save(ArtifactsDir + "Document.TextWatermark.docx");

// Vi kan ta bort en vattenstämpel från ett dokument som detta.
if (doc.Watermark.Type == WatermarkType.Text)
    doc.Watermark.Remove();
```

### Se även

* namnutrymme [Aspose.Words](../../aspose.words/)
* hopsättning [Aspose.Words](../../)


