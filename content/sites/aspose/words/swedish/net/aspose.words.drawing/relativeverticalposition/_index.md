---
title: Enum RelativeVerticalPosition
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.Drawing.RelativeVerticalPosition uppräkning. Anger vad den vertikala positionen för en form eller textram är relativ.
type: docs
weight: 1070
url: /sv/net/aspose.words.drawing/relativeverticalposition/
---
## RelativeVerticalPosition enumeration

Anger vad den vertikala positionen för en form eller textram är relativ.

```csharp
public enum RelativeVerticalPosition
```

### Värderingar

| namn | Värde | Beskrivning |
| --- | --- | --- |
| Margin | `0` | Anger att den vertikala positioneringen ska vara relativt sidmarginalerna. |
| Page | `1` | Objektet är placerat i förhållande till sidans övre kant. |
| Paragraph | `2` | Objektet är placerat i förhållande till toppen av stycket som innehåller ankaret. |
| Line | `3` | Odokumenterad. |
| TopMargin | `4` | Anger att den vertikala positioneringen ska vara relativt den övre marginalen på den aktuella sidan. |
| BottomMargin | `5` | Anger att den vertikala positioneringen ska vara relativt den nedre marginalen på den aktuella sidan. |
| InsideMargin | `6` | Anger att den vertikala positioneringen ska vara relativt den inre marginalen på den aktuella sidan. |
| OutsideMargin | `7` | Anger att den vertikala positioneringen ska vara relativt den yttre marginalen på den aktuella sidan. |
| TableDefault | `0` | Standardvärdet ärMargin . |
| TextFrameDefault | `2` | Standardvärdet ärParagraph . |

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

* property [RelativeVerticalPosition](../shapebase/relativeverticalposition/)
* namnutrymme [Aspose.Words.Drawing](../../aspose.words.drawing/)
* hopsättning [Aspose.Words](../../)


