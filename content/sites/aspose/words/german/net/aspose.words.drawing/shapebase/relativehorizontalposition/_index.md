---
title: ShapeBase.RelativeHorizontalPosition
second_title: Aspose.Words für .NET-API-Referenz
description: ShapeBase eigendom. Gibt an in welchem Verhältnis die Form horizontal positioniert ist.
type: docs
weight: 400
url: /de/net/aspose.words.drawing/shapebase/relativehorizontalposition/
---
## ShapeBase.RelativeHorizontalPosition property

Gibt an, in welchem Verhältnis die Form horizontal positioniert ist.

```csharp
public RelativeHorizontalPosition RelativeHorizontalPosition { get; set; }
```

### Bemerkungen

Der Standardwert istColumn.

Hat nur Auswirkungen auf schwebende Formen der obersten Ebene.

### Beispiele

Zeigt, wie ein schwebendes Bild in der Mitte einer Seite eingefügt wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Fügen Sie ein schwebendes Bild ein, das hinter dem überlappenden Text angezeigt wird, und richten Sie es an der Mitte der Seite aus.
Shape shape = builder.InsertImage(ImageDir + "Logo.jpg");
shape.WrapType = WrapType.None;
shape.BehindText = true;
shape.RelativeHorizontalPosition = RelativeHorizontalPosition.Page;
shape.RelativeVerticalPosition = RelativeVerticalPosition.Page;
shape.HorizontalAlignment = HorizontalAlignment.Center;
shape.VerticalAlignment = VerticalAlignment.Center;

doc.Save(ArtifactsDir + "Image.CreateFloatingPageCenter.docx");
```

### Siehe auch

* enum [RelativeHorizontalPosition](../../relativehorizontalposition/)
* class [ShapeBase](../)
* namensraum [Aspose.Words.Drawing](../../shapebase/)
* Montage [Aspose.Words](../../../)


