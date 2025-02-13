---
title: ShapeBase.IsMoveToRevision
second_title: Aspose.Words för .NET API Referens
description: ShapeBase fast egendom. Returnerar Sann om detta objekt flyttades infogades i Microsoft Word medan ändringsspårning var aktiverad.
type: docs
weight: 320
url: /sv/net/aspose.words.drawing/shapebase/ismovetorevision/
---
## ShapeBase.IsMoveToRevision property

Returnerar **Sann** om detta objekt flyttades (infogades) i Microsoft Word medan ändringsspårning var aktiverad.

```csharp
public bool IsMoveToRevision { get; }
```

### Exempel

Visar hur man identifierar flyttversionsformer.

```csharp
// En flyttversion är när vi flyttar ett element i dokumentets brödtext genom att klippa ut och klistra in det i Microsoft Word medan
// spåra ändringar. Om vi involverar en inline-form i en sådan textrörelse blir den formen också en revidering.
// Att kopiera och klistra eller flytta flytande former skapar inte flyttändringar.
Document doc = new Document(MyDir + "Revision shape.docx");

// Flytta revisioner består av par av "Flytta från" och "Flytta till" versioner. Vi flyttade in det här dokumentet i en form,
// men tills vi accepterar eller avvisar flyttrevisionen kommer det att finnas två instanser av den formen.
Shape[] shapes = doc.GetChildNodes(NodeType.Shape, true).OfType<Shape>().ToArray();

Assert.AreEqual(2, shapes.Length);

// Detta är "Flytta till"-revisionen, som är formen vid ankomstdestinationen.
// Om vi accepterar revisionen kommer denna "Flytta till" versionsform att försvinna,
// och versionsformen "Flytta från" kommer att finnas kvar.
Assert.False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

// Detta är versionen "Flytta från", som är formen på sin ursprungliga plats.
// Om vi accepterar revisionen kommer denna "Flytta från" versionsform att försvinna,
// och versionsformen "Flytta till" kommer att finnas kvar.
Assert.True(shapes[1].IsMoveFromRevision);
Assert.False(shapes[1].IsMoveToRevision);
```

### Se även

* class [ShapeBase](../)
* namnutrymme [Aspose.Words.Drawing](../../shapebase/)
* hopsättning [Aspose.Words](../../../)


