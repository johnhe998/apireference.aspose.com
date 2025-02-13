---
title: Class Stroke
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.Drawing.Stroke klass. Definierar ett streck för en form.
type: docs
weight: 1160
url: /sv/net/aspose.words.drawing/stroke/
---
## Stroke class

Definierar ett streck för en form.

```csharp
public class Stroke
```

## Egenskaper

| namn | Beskrivning |
| --- | --- |
| [BackColor](../../aspose.words.drawing/stroke/backcolor/) { get; set; } | Hämtar eller ställer in bakgrundsfärgen för strecket. |
| [Color](../../aspose.words.drawing/stroke/color/) { get; set; } | Definierar färgen på ett streck. |
| [Color2](../../aspose.words.drawing/stroke/color2/) { get; set; } | Definierar en andra färg för en linje. |
| [DashStyle](../../aspose.words.drawing/stroke/dashstyle/) { get; set; } | Anger punkt- och streckmönstret för ett streck. |
| [EndArrowLength](../../aspose.words.drawing/stroke/endarrowlength/) { get; set; } | Definierar pilspetsens längd för slutet av ett slag. |
| [EndArrowType](../../aspose.words.drawing/stroke/endarrowtype/) { get; set; } | Definierar pilspetsen för slutet av ett streck. |
| [EndArrowWidth](../../aspose.words.drawing/stroke/endarrowwidth/) { get; set; } | Definierar pilspetsens bredd för slutet av ett streck. |
| [EndCap](../../aspose.words.drawing/stroke/endcap/) { get; set; } | Definierar cap-stilen för slutet av ett streck. |
| [ForeColor](../../aspose.words.drawing/stroke/forecolor/) { get; set; } | Hämtar eller ställer in linjens förgrundsfärg. |
| [ImageBytes](../../aspose.words.drawing/stroke/imagebytes/) { get; } | Definierar bilden för en linjebild eller mönsterfyllning. |
| [JoinStyle](../../aspose.words.drawing/stroke/joinstyle/) { get; set; } | Definierar kopplingsstilen för en polylinje. |
| [LineStyle](../../aspose.words.drawing/stroke/linestyle/) { get; set; } | Definierar linjestilen för strecket. |
| [On](../../aspose.words.drawing/stroke/on/) { get; set; } | Definierar om sökvägen ska streckas. |
| [Opacity](../../aspose.words.drawing/stroke/opacity/) { get; set; } | Definierar graden av genomskinlighet för ett streck. Giltigt intervall är från 0 till 1. |
| [StartArrowLength](../../aspose.words.drawing/stroke/startarrowlength/) { get; set; } | Definierar pilspetsens längd för början av ett slag. |
| [StartArrowType](../../aspose.words.drawing/stroke/startarrowtype/) { get; set; } | Definierar pilspetsen för starten av ett slag. |
| [StartArrowWidth](../../aspose.words.drawing/stroke/startarrowwidth/) { get; set; } | Definierar pilspetsens bredd för början av ett slag. |
| [Transparency](../../aspose.words.drawing/stroke/transparency/) { get; set; } | Hämtar eller ställer in ett värde mellan 0,0 (opak) och 1,0 (clear) som representerar graden av transparens för linjen. |
| [Visible](../../aspose.words.drawing/stroke/visible/) { get; set; } | Hämtar eller ställer in en flagga som indikerar om strecket är synligt. |
| [Weight](../../aspose.words.drawing/stroke/weight/) { get; set; } | Definierar penseltjockleken som sträcker banan för en form i punkter. |

### Anmärkningar

Använd[`Stroke`](../shape/stroke/)egenskap för att komma åt strokeegenskaper för en shape. Du skapar inte instanser av`Stroke` klass direkt.

### Exempel

Visar hur man ändrar slagegenskaper.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertShape(ShapeType.Rectangle, RelativeHorizontalPosition.LeftMargin, 100,
    RelativeVerticalPosition.TopMargin, 100, 200, 200, WrapType.None);

// Grundformer, som rektangeln, har två synliga delar.
// 1 - Fyllningen, som gäller området inom konturen av formen:
shape.Fill.ForeColor = Color.White;

// 2 - Stroget, som markerar konturen av formen:
// Ändra olika egenskaper för denna forms streck.
Stroke stroke = shape.Stroke;
stroke.On = true;
stroke.Weight = 5;
stroke.Color = Color.Red;
stroke.DashStyle = DashStyle.ShortDashDotDot;
stroke.JoinStyle = JoinStyle.Miter;
stroke.EndCap = EndCap.Square;
stroke.LineStyle = ShapeLineStyle.Triple;

doc.Save(ArtifactsDir + "Shape.Stroke.docx");
```

### Se även

* namnutrymme [Aspose.Words.Drawing](../../aspose.words.drawing/)
* hopsättning [Aspose.Words](../../)


