---
title: ShapeBase.Bottom
second_title: Aspose.Words für .NET-API-Referenz
description: ShapeBase eigendom. Ruft die Position der Unterkante des umgebenden Blocks der Form ab.
type: docs
weight: 60
url: /de/net/aspose.words.drawing/shapebase/bottom/
---
## ShapeBase.Bottom property

Ruft die Position der Unterkante des umgebenden Blocks der Form ab.

```csharp
public double Bottom { get; }
```

### Bemerkungen

Bei einer Form der obersten Ebene wird der Wert in Punkten angegeben und ist relativ zum Formanker.

Bei Formen in einer Gruppe befindet sich der Wert im Koordinatenraum und in den Einheiten der übergeordneten Gruppe.

### Beispiele

Zeigt, wie Sie ein schwebendes Bild einfügen und seine Position und Größe angeben.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertImage(ImageDir + "Logo.jpg");
shape.WrapType = WrapType.None;

// Konfigurieren Sie die Eigenschaft "RelativeHorizontalPosition" der Form, um den Wert der Eigenschaft "Left" zu behandeln
 // als horizontaler Abstand der Form in Punkten von der linken Seite der Seite.
shape.RelativeHorizontalPosition = RelativeHorizontalPosition.Page;

// Legen Sie den horizontalen Abstand der Form von der linken Seite der Seite auf 100 fest.
shape.Left = 100;

// Verwenden Sie die Eigenschaft "RelativeVerticalPosition" auf ähnliche Weise, um die Form 80 pt unter dem oberen Rand der Seite zu positionieren.
shape.RelativeVerticalPosition = RelativeVerticalPosition.Page;
shape.Top = 80;

// Legen Sie die Höhe der Form fest, wodurch die Breite automatisch skaliert wird, um die Abmessungen beizubehalten.
shape.Height = 125;

Assert.AreEqual(125.0d, shape.Width);

// Die Eigenschaften "Bottom" und "Right" enthalten den unteren und rechten Rand des Bildes.
Assert.AreEqual(shape.Top + shape.Height, shape.Bottom);
Assert.AreEqual(shape.Left + shape.Width, shape.Right);

doc.Save(ArtifactsDir + "Image.CreateFloatingPositionSize.docx");
```

### Siehe auch

* class [ShapeBase](../)
* namensraum [Aspose.Words.Drawing](../../shapebase/)
* Montage [Aspose.Words](../../../)


