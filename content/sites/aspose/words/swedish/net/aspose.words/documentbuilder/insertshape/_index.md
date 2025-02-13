---
title: DocumentBuilder.InsertShape
second_title: Aspose.Words för .NET API Referens
description: DocumentBuilder metod. Infogar inline form med angiven typ och storlek.
type: docs
weight: 410
url: /sv/net/aspose.words/documentbuilder/insertshape/
---
## InsertShape(ShapeType, double, double) {#insertshape_1}

Infogar inline form med angiven typ och storlek.

```csharp
public Shape InsertShape(ShapeType shapeType, double width, double height)
```

| Parameter | Typ | Beskrivning |
| --- | --- | --- |
| shapeType | ShapeType | Formtypen som ska infogas i dokumentet. |
| width | Double | Formens bredd i punkter. |
| height | Double | Formens höjd i punkter. |

### Returvärde

Formnoden som infogades.

### Exempel

Visar hur man infogar DML-former i ett dokument.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Nedan finns två typer av omslag som former kan ha.
// 1 - Flytande:
builder.InsertShape(ShapeType.TopCornersRounded, RelativeHorizontalPosition.Page, 100, 
        RelativeVerticalPosition.Page, 100, 50, 50, WrapType.None);

// 2 - Inline:
builder.InsertShape(ShapeType.DiagonalCornersRounded, 50, 50);

// Om du behöver skapa "icke-primitiva" former, som SingleCornerSnipped, TopCornersSnipped, DiagonalCornersSnipped,
// TopCornersOneRoundedOneSnipped, SingleCornerRounded, TopCornersRounded eller DiagonalCornersRounded,
// spara sedan dokumentet med "Strict" eller "Transitional" compliance, vilket gör det möjligt att spara form som DML.
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx);
saveOptions.Compliance = OoxmlCompliance.Iso29500_2008_Transitional;

doc.Save(ArtifactsDir + "Shape.ShapeInsertion.docx", saveOptions);
```

### Se även

* class [Shape](../../../aspose.words.drawing/shape/)
* enum [ShapeType](../../../aspose.words.drawing/shapetype/)
* class [DocumentBuilder](../)
* namnutrymme [Aspose.Words](../../documentbuilder/)
* hopsättning [Aspose.Words](../../../)

---

## InsertShape(ShapeType, RelativeHorizontalPosition, double, RelativeVerticalPosition, double, double, double, WrapType) {#insertshape}

Infogar fritt svävande form med angiven position, storlek och typ av textbrytning.

```csharp
public Shape InsertShape(ShapeType shapeType, RelativeHorizontalPosition horzPos, double left, 
    RelativeVerticalPosition vertPos, double top, double width, double height, WrapType wrapType)
```

| Parameter | Typ | Beskrivning |
| --- | --- | --- |
| shapeType | ShapeType | Formtypen som ska infogas i dokumentet |
| horzPos | RelativeHorizontalPosition | Anger varifrån det horisontella avståndet till formen mäts. |
| left | Double | Avstånd i punkter från origo till vänster sida av formen. |
| vertPos | RelativeVerticalPosition | Anger varifrån det vertikala avståndet till formen mäts. |
| top | Double | Avstånd i punkter från origo till formens översida. |
| width | Double | Formens bredd i punkter. |
| height | Double | Formens bredd i punkter. |
| wrapType | WrapType | Anger hur text lindas runt formen. |

### Returvärde

Formnoden som infogades.

### Exempel

Visar hur man infogar DML-former i ett dokument.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Nedan finns två typer av omslag som former kan ha.
// 1 - Flytande:
builder.InsertShape(ShapeType.TopCornersRounded, RelativeHorizontalPosition.Page, 100, 
        RelativeVerticalPosition.Page, 100, 50, 50, WrapType.None);

// 2 - Inline:
builder.InsertShape(ShapeType.DiagonalCornersRounded, 50, 50);

// Om du behöver skapa "icke-primitiva" former, som SingleCornerSnipped, TopCornersSnipped, DiagonalCornersSnipped,
// TopCornersOneRoundedOneSnipped, SingleCornerRounded, TopCornersRounded eller DiagonalCornersRounded,
// spara sedan dokumentet med "Strict" eller "Transitional" compliance, vilket gör det möjligt att spara form som DML.
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx);
saveOptions.Compliance = OoxmlCompliance.Iso29500_2008_Transitional;

doc.Save(ArtifactsDir + "Shape.ShapeInsertion.docx", saveOptions);
```

### Se även

* class [Shape](../../../aspose.words.drawing/shape/)
* enum [ShapeType](../../../aspose.words.drawing/shapetype/)
* enum [RelativeHorizontalPosition](../../../aspose.words.drawing/relativehorizontalposition/)
* enum [RelativeVerticalPosition](../../../aspose.words.drawing/relativeverticalposition/)
* enum [WrapType](../../../aspose.words.drawing/wraptype/)
* class [DocumentBuilder](../)
* namnutrymme [Aspose.Words](../../documentbuilder/)
* hopsättning [Aspose.Words](../../../)


