---
title: ShapeBase.MarkupLanguage
second_title: Aspose.Words für .NET-API-Referenz
description: ShapeBase eigendom. Ruft die für dieses Grafikobjekt verwendete MarkupLanguage ab.
type: docs
weight: 370
url: /de/net/aspose.words.drawing/shapebase/markuplanguage/
---
## ShapeBase.MarkupLanguage property

Ruft die für dieses Grafikobjekt verwendete MarkupLanguage ab.

```csharp
public ShapeMarkupLanguage MarkupLanguage { get; }
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

* enum [ShapeMarkupLanguage](../../shapemarkuplanguage/)
* class [ShapeBase](../)
* namensraum [Aspose.Words.Drawing](../../shapebase/)
* Montage [Aspose.Words](../../../)


