---
title: GradientStopCollection.RemoveAt
second_title: Aspose.Words för .NET API Referens
description: GradientStopCollection metod. Tar bort enGradientStopfrån samlingen vid ett specificerat index.
type: docs
weight: 70
url: /sv/net/aspose.words.drawing/gradientstopcollection/removeat/
---
## GradientStopCollection.RemoveAt method

Tar bort en[`GradientStop`](../../gradientstop/)från samlingen vid ett specificerat index.

```csharp
public GradientStop RemoveAt(int index)
```

### Returvärde

Tog bort[`GradientStop`](../../gradientstop/).

### Exempel

Visar hur man lägger till övertoningsstopp i övertoningsfyllningen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertShape(ShapeType.Rectangle, 80, 80);
shape.Fill.TwoColorGradient(Color.Green, Color.Red, GradientStyle.Horizontal, GradientVariant.Variant2);

// Få gradient stoppar samling.
GradientStopCollection gradientStops = shape.Fill.GradientStops;

// Ändra första gradientstopp.
gradientStops[0].Color = Color.Aqua;
gradientStops[0].Position = 0.1;
gradientStops[0].Transparency = 0.25;

// Lägg till nytt övertoningsstopp i slutet av samlingen.
GradientStop gradientStop = new GradientStop(Color.Brown, 0.5);
gradientStops.Add(gradientStop);

// Ta bort gradientstopp vid index 1.
gradientStops.RemoveAt(1);
// Och infoga nytt gradientstopp vid samma index 1.
gradientStops.Insert(1, new GradientStop(Color.Chocolate, 0.75, 0.3));

// Ta bort sista gradientstopp i samlingen.
gradientStop = gradientStops[2];
gradientStops.Remove(gradientStop);

Assert.AreEqual(2, gradientStops.Count);

Assert.AreEqual(Color.Aqua.ToArgb(), gradientStops[0].Color.ToArgb());
Assert.AreEqual(0.1d, gradientStops[0].Position, 0.01d);
Assert.AreEqual(0.25d, gradientStops[0].Transparency, 0.01d);

Assert.AreEqual(Color.Chocolate.ToArgb(), gradientStops[1].Color.ToArgb());
Assert.AreEqual(0.75d, gradientStops[1].Position, 0.01d);
Assert.AreEqual(0.3d, gradientStops[1].Transparency, 0.01d);

// Använd efterlevnadsalternativet för att definiera formen med DML
// om du vill få egenskapen "GradientStops" efter att dokumentet har sparats.
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Strict };

doc.Save(ArtifactsDir + "Shape.GradientStops.docx", saveOptions);
```

### Se även

* class [GradientStop](../../gradientstop/)
* class [GradientStopCollection](../)
* namnutrymme [Aspose.Words.Drawing](../../gradientstopcollection/)
* hopsättning [Aspose.Words](../../../)


