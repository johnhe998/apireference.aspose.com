---
title: Enum RelativeHorizontalPosition
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.Drawing.RelativeHorizontalPosition uppräkning. Anger vad den horisontella positionen för en form eller textram är relativ.
type: docs
weight: 1060
url: /sv/net/aspose.words.drawing/relativehorizontalposition/
---
## RelativeHorizontalPosition enumeration

Anger vad den horisontella positionen för en form eller textram är relativ.

```csharp
public enum RelativeHorizontalPosition
```

### Värderingar

| namn | Värde | Beskrivning |
| --- | --- | --- |
| Margin | `0` | Anger att den horisontella positioneringen ska vara relativt sidmarginalerna. |
| Page | `1` | Objektet är placerat i förhållande till sidans vänstra kant. |
| Column | `2` | Objektet är placerat i förhållande till vänster sida av kolumnen. |
| Character | `3` | Objektet är placerat i förhållande till vänster sida av stycket. |
| LeftMargin | `4` | Anger att den horisontella positioneringen ska vara relativt sidans vänstra marginal. |
| RightMargin | `5` | Anger att den horisontella positioneringen ska vara relativt högermarginalen på sidan. |
| InsideMargin | `6` | Anger att den horisontella positioneringen ska vara relativt den inre marginalen på den aktuella sidan (vänstermarginalen på udda sidor, höger på jämna sidor). |
| OutsideMargin | `7` | Anger att den horisontella positioneringen ska vara relativt den yttre marginalen på den aktuella sidan (högermarginalen på udda sidor, vänster på jämna sidor). |
| Default | `2` | Standardvärdet ärColumn . |

### Exempel

Visar hur man infogar en flytande bild i mitten av en sida.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Infoga en flytande bild som kommer att visas bakom den överlappande texten och justera den mot sidans mitt.
Shape shape = builder.InsertImage(ImageDir + "Logo.jpg");
shape.WrapType = WrapType.None;
shape.BehindText = true;
shape.RelativeHorizontalPosition = RelativeHorizontalPosition.Page;
shape.RelativeVerticalPosition = RelativeVerticalPosition.Page;
shape.HorizontalAlignment = HorizontalAlignment.Center;
shape.VerticalAlignment = VerticalAlignment.Center;

doc.Save(ArtifactsDir + "Image.CreateFloatingPageCenter.docx");
```

Visar hur man infogar en bild och använder den som vattenstämpel.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Infoga bilden i rubriken så att den syns på varje sida.
Image image = Image.FromFile(ImageDir + "Transparent background logo.png");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
Shape shape = builder.InsertImage(image);
shape.WrapType = WrapType.None;
shape.BehindText = true;

// Placera bilden i mitten av sidan.
shape.RelativeHorizontalPosition = RelativeHorizontalPosition.Page;
shape.RelativeVerticalPosition = RelativeVerticalPosition.Page;
shape.Left = (builder.PageSetup.PageWidth - shape.Width) / 2;
shape.Top = (builder.PageSetup.PageHeight - shape.Height) / 2;

doc.Save(ArtifactsDir + "DocumentBuilder.InsertWatermark.docx");
```

Visar hur man infogar en bild och använder den som vattenstämpel (.NetStandard 2.0).

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Infoga bilden i rubriken så att den syns på varje sida.
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);

using (SKBitmap image = SKBitmap.Decode(ImageDir + "Transparent background logo.png"))
{
    builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
    Shape shape = builder.InsertImage(image);
    shape.WrapType = WrapType.None;
    shape.BehindText = true;

    // Placera bilden i mitten av sidan.
    shape.RelativeHorizontalPosition = RelativeHorizontalPosition.Page;
    shape.RelativeVerticalPosition = RelativeVerticalPosition.Page;
    shape.Left = (builder.PageSetup.PageWidth - shape.Width) / 2;
    shape.Top = (builder.PageSetup.PageHeight - shape.Height) / 2;
}

doc.Save(ArtifactsDir + "DocumentBuilder.InsertWatermarkNetStandard2.docx");
```

### Se även

* property [RelativeHorizontalPosition](../shapebase/relativehorizontalposition/)
* namnutrymme [Aspose.Words.Drawing](../../aspose.words.drawing/)
* hopsättning [Aspose.Words](../../)


