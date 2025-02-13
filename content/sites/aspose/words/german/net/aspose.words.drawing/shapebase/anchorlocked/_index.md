---
title: ShapeBase.AnchorLocked
second_title: Aspose.Words für .NET-API-Referenz
description: ShapeBase eigendom. Gibt an ob der Anker der Form gesperrt ist.
type: docs
weight: 30
url: /de/net/aspose.words.drawing/shapebase/anchorlocked/
---
## ShapeBase.AnchorLocked property

Gibt an, ob der Anker der Form gesperrt ist.

```csharp
public bool AnchorLocked { get; set; }
```

### Bemerkungen

Der Standardwert ist **FALSCH**.

Hat nur Auswirkungen auf Shapes der obersten Ebene.

Diese Eigenschaft wirkt sich auf das Verhalten des Ankers der Form in Microsoft Word aus. Wenn der Anker nicht gesperrt ist, kann das Verschieben der Form in Microsoft Word auch den Anker der Form verschieben .

### Beispiele

Zeigt, wie der Absatzanker einer Form gesperrt oder entsperrt wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Hello world!");

builder.Write("Our shape will have an anchor attached to this paragraph.");
Shape shape = builder.InsertShape(ShapeType.Rectangle, 200, 160);
shape.WrapType = WrapType.None;
builder.InsertBreak(BreakType.ParagraphBreak);

builder.Writeln("Hello again!");

// Setzen Sie die Eigenschaft "AnchorLocked" auf "true", um den Anker der Form zu verhindern
// vom Verschieben beim Verschieben der Form in Microsoft Word.
// Setzen Sie die Eigenschaft "AnchorLocked" auf "false", um jede Bewegung der Form zuzulassen
// um seinen Anker auch zu einem anderen Absatz zu verschieben, in dessen Nähe die Form endet.
shape.AnchorLocked = anchorLocked;

// Wenn die Form links kein sichtbares Ankersymbol hat,
// Wir müssen sichtbare Anker über "Optionen" aktivieren -> "Anzeigen" -> "Objektanker".
doc.Save(ArtifactsDir + "Shape.AnchorLocked.docx");
```

### Siehe auch

* class [ShapeBase](../)
* namensraum [Aspose.Words.Drawing](../../shapebase/)
* Montage [Aspose.Words](../../../)


