---
title: Fill.Patterned
second_title: Aspose.Words für .NET-API-Referenz
description: Fill methode. Legt die angegebene Füllung auf ein Muster fest.
type: docs
weight: 170
url: /de/net/aspose.words.drawing/fill/patterned/
---
## Patterned(PatternType) {#patterned}

Legt die angegebene Füllung auf ein Muster fest.

```csharp
public void Patterned(PatternType patternType)
```

| Parameter | Typ | Beschreibung |
| --- | --- | --- |
| patternType | PatternType | [`PatternType`](../../patterntype/) |

### Beispiele

Zeigt, wie Muster für eine Form festgelegt werden.

```csharp
Document doc = new Document(MyDir + "Shape stroke pattern border.docx");

Shape shape = (Shape)doc.GetChild(NodeType.Shape, 0, true);
Fill fill = shape.Fill;

Console.WriteLine("Pattern value is: {0}", fill.Pattern);

// Es gibt mehrere Möglichkeiten, ein Muster zu füllen.
// 1 - Muster auf die Formfüllung anwenden:
fill.Patterned(PatternType.DiagonalBrick);

// 2 - Muster mit Vorder- und Hintergrundfarbe auf die Formfüllung anwenden:
fill.Patterned(PatternType.DiagonalBrick, Color.Aqua, Color.Bisque);

doc.Save(ArtifactsDir + "Shape.FillPattern.docx");
```

### Siehe auch

* enum [PatternType](../../patterntype/)
* class [Fill](../)
* namensraum [Aspose.Words.Drawing](../../fill/)
* Montage [Aspose.Words](../../../)

---

## Patterned(PatternType, Color, Color) {#patterned_1}

Legt die angegebene Füllung auf ein Muster fest.

```csharp
public void Patterned(PatternType patternType, Color foreColor, Color backColor)
```

| Parameter | Typ | Beschreibung |
| --- | --- | --- |
| patternType | PatternType | [`PatternType`](../../patterntype/) |
| foreColor | Color | Die Farbe der Vordergrundfüllung. |
| backColor | Color | Die Farbe der Hintergrundfüllung. |

### Beispiele

Zeigt, wie Muster für eine Form festgelegt werden.

```csharp
Document doc = new Document(MyDir + "Shape stroke pattern border.docx");

Shape shape = (Shape)doc.GetChild(NodeType.Shape, 0, true);
Fill fill = shape.Fill;

Console.WriteLine("Pattern value is: {0}", fill.Pattern);

// Es gibt mehrere Möglichkeiten, ein Muster zu füllen.
// 1 - Muster auf die Formfüllung anwenden:
fill.Patterned(PatternType.DiagonalBrick);

// 2 - Muster mit Vorder- und Hintergrundfarbe auf die Formfüllung anwenden:
fill.Patterned(PatternType.DiagonalBrick, Color.Aqua, Color.Bisque);

doc.Save(ArtifactsDir + "Shape.FillPattern.docx");
```

### Siehe auch

* enum [PatternType](../../patterntype/)
* class [Fill](../)
* namensraum [Aspose.Words.Drawing](../../fill/)
* Montage [Aspose.Words](../../../)


