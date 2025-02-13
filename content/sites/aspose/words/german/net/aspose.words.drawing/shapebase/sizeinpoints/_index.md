---
title: ShapeBase.SizeInPoints
second_title: Aspose.Words für .NET-API-Referenz
description: ShapeBase eigendom. Ruft die Größe der Form in Punkten ab.
type: docs
weight: 470
url: /de/net/aspose.words.drawing/shapebase/sizeinpoints/
---
## ShapeBase.SizeInPoints property

Ruft die Größe der Form in Punkten ab.

```csharp
public SizeF SizeInPoints { get; }
```

### Beispiele

Zeigt, wie Sie die Größe und Auszeichnungssprache einer Form überprüfen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertImage(ImageDir + "Transparent background logo.png");

Assert.AreEqual(ShapeMarkupLanguage.Dml, shape.MarkupLanguage);
Assert.AreEqual(new SizeF(300, 300), shape.SizeInPoints);
```

### Siehe auch

* class [ShapeBase](../)
* namensraum [Aspose.Words.Drawing](../../shapebase/)
* Montage [Aspose.Words](../../../)


