---
title: ShapeBase.IsTopLevel
second_title: Aspose.Words för .NET API Referens
description: ShapeBase fast egendom. Returnerar sant om denna form inte är ett underordnat till en gruppform.
type: docs
weight: 340
url: /sv/net/aspose.words.drawing/shapebase/istoplevel/
---
## ShapeBase.IsTopLevel property

Returnerar sant om denna form inte är ett underordnat till en gruppform.

```csharp
public bool IsTopLevel { get; }
```

### Exempel

Visar hur man avgör om en form är en del av en gruppform.

```csharp
Document doc = new Document();

Shape shape = new Shape(doc, ShapeType.Rectangle);
shape.Width = 200;
shape.Height = 200;
shape.WrapType = WrapType.None;

// En form är som standard inte en del av någon gruppform och har därför egenskapen "IsTopLevel" inställd på "true".
Assert.True(shape.IsTopLevel);

GroupShape group = new GroupShape(doc);
group.AppendChild(shape);

// När vi har assimilerat en form till en gruppform ändras egenskapen "IsTopLevel" till "false".
Assert.False(shape.IsTopLevel);
```

### Se även

* class [ShapeBase](../)
* namnutrymme [Aspose.Words.Drawing](../../shapebase/)
* hopsättning [Aspose.Words](../../../)


