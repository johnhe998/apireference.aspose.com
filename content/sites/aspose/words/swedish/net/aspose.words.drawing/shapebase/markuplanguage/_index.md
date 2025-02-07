---
title: ShapeBase.MarkupLanguage
second_title: Aspose.Words för .NET API Referens
description: ShapeBase fast egendom. Får MarkupLanguage som används för detta grafiska objekt.
type: docs
weight: 370
url: /sv/net/aspose.words.drawing/shapebase/markuplanguage/
---
## ShapeBase.MarkupLanguage property

Får MarkupLanguage som används för detta grafiska objekt.

```csharp
public ShapeMarkupLanguage MarkupLanguage { get; }
```

### Exempel

Visar hur du verifierar en forms storlek och märkningsspråk.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertImage(ImageDir + "Transparent background logo.png");

Assert.AreEqual(ShapeMarkupLanguage.Dml, shape.MarkupLanguage);
Assert.AreEqual(new SizeF(300, 300), shape.SizeInPoints);
```

### Se även

* enum [ShapeMarkupLanguage](../../shapemarkuplanguage/)
* class [ShapeBase](../)
* namnutrymme [Aspose.Words.Drawing](../../shapebase/)
* hopsättning [Aspose.Words](../../../)


