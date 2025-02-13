---
title: ShapeBase.RelativeHorizontalPosition
second_title: Aspose.Words för .NET API Referens
description: ShapeBase fast egendom. Anger i förhållande till vad formen är placerad horisontellt.
type: docs
weight: 400
url: /sv/net/aspose.words.drawing/shapebase/relativehorizontalposition/
---
## ShapeBase.RelativeHorizontalPosition property

Anger i förhållande till vad formen är placerad horisontellt.

```csharp
public RelativeHorizontalPosition RelativeHorizontalPosition { get; set; }
```

### Anmärkningar

Standardvärdet ärColumn.

Har effekt endast för svävande former på toppnivå.

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

### Se även

* enum [RelativeHorizontalPosition](../../relativehorizontalposition/)
* class [ShapeBase](../)
* namnutrymme [Aspose.Words.Drawing](../../shapebase/)
* hopsättning [Aspose.Words](../../../)


