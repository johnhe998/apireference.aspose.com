---
title: ShapeBase.Left
second_title: Aspose.Words för .NET API Referens
description: ShapeBase fast egendom. Hämtar eller ställer in positionen för den vänstra kanten av formens innehållsblock.
type: docs
weight: 360
url: /sv/net/aspose.words.drawing/shapebase/left/
---
## ShapeBase.Left property

Hämtar eller ställer in positionen för den vänstra kanten av formens innehållsblock.

```csharp
public double Left { get; set; }
```

### Anmärkningar

För en form på toppnivå är värdet i punkter och i förhållande till formankaret.

För former i en grupp finns värdet i koordinatutrymmet och enheterna för den överordnade gruppen.

Standardvärdet är 0.

Har effekt endast för flytande former.

### Exempel

Visar hur man infogar en flytande bild och anger dess position och storlek.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertImage(ImageDir + "Logo.jpg");
shape.WrapType = WrapType.None;

// Konfigurera formens "RelativeHorizontalPosition"-egenskap för att behandla värdet på egenskapen "Left"
 // som formens horisontella avstånd, i punkter, från sidans vänstra sida.
shape.RelativeHorizontalPosition = RelativeHorizontalPosition.Page;

// Ställ in formens horisontella avstånd från sidans vänstra sida till 100.
shape.Left = 100;

// Använd egenskapen "RelativeVerticalPosition" på liknande sätt för att placera formen 80 pkt under toppen av sidan.
shape.RelativeVerticalPosition = RelativeVerticalPosition.Page;
shape.Top = 80;

// Ställ in formens höjd, vilket automatiskt skalar bredden för att bevara dimensionerna.
shape.Height = 125;

Assert.AreEqual(125.0d, shape.Width);

// Egenskaperna "Bottom" och "Right" innehåller bildens nedre och högra kanter.
Assert.AreEqual(shape.Top + shape.Height, shape.Bottom);
Assert.AreEqual(shape.Left + shape.Width, shape.Right);

doc.Save(ArtifactsDir + "Image.CreateFloatingPositionSize.docx");
```

### Se även

* class [ShapeBase](../)
* namnutrymme [Aspose.Words.Drawing](../../shapebase/)
* hopsättning [Aspose.Words](../../../)


