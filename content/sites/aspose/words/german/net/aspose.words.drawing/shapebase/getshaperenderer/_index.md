---
title: ShapeBase.GetShapeRenderer
second_title: Aspose.Words für .NET-API-Referenz
description: ShapeBase methode. Erstellt ein Objekt und gibt es zurück das verwendet werden kann um diese Form in ein Bild zu rendern.
type: docs
weight: 600
url: /de/net/aspose.words.drawing/shapebase/getshaperenderer/
---
## ShapeBase.GetShapeRenderer method

Erstellt ein Objekt und gibt es zurück, das verwendet werden kann, um diese Form in ein Bild zu rendern.

```csharp
public ShapeRenderer GetShapeRenderer()
```

### Rückgabewert

Das Rendererobjekt für diese Form.

### Bemerkungen

Diese Methode ruft nur die auf[`ShapeRenderer`](../../../aspose.words.rendering/shaperenderer/) Konstruktor und übergibt dieses Objekt als Parameter.

### Beispiele

Zeigt, wie Sie einen Form-Renderer verwenden, um Formen in Dateien im lokalen Dateisystem zu exportieren.

```csharp
Document doc = new Document(MyDir + "Various shapes.docx");
Shape[] shapes = doc.GetChildNodes(NodeType.Shape, true).OfType<Shape>().ToArray();

Assert.AreEqual(7, shapes.Length);

// Das Dokument enthält 7 Formen, darunter eine Gruppenform mit 2 untergeordneten Formen.
// Wir rendern jede Form in eine Bilddatei im lokalen Dateisystem
// während die Gruppenformen ignoriert werden, da sie nicht erscheinen.
// Dies erzeugt 6 Bilddateien.
foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true).OfType<Shape>())
{
    ShapeRenderer renderer = shape.GetShapeRenderer();
    ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Png);
    renderer.Save(ArtifactsDir + $"Shape.RenderAllShapes.{shape.Name}.png", options);
}
```

### Siehe auch

* class [ShapeRenderer](../../../aspose.words.rendering/shaperenderer/)
* class [ShapeBase](../)
* namensraum [Aspose.Words.Drawing](../../shapebase/)
* Montage [Aspose.Words](../../../)


