---
title: NodeRendererBase.GetOpaqueBoundsInPixels
second_title: Aspose.Words für .NET-API-Referenz
description: NodeRendererBase methode. Berechnet die undurchsichtigen Grenzen der Form in Pixeln für einen angegebenen Zoomfaktor und eine angegebene Auflösung.
type: docs
weight: 50
url: /de/net/aspose.words.rendering/noderendererbase/getopaqueboundsinpixels/
---
## GetOpaqueBoundsInPixels(float, float) {#getopaqueboundsinpixels}

Berechnet die undurchsichtigen Grenzen der Form in Pixeln für einen angegebenen Zoomfaktor und eine angegebene Auflösung.

```csharp
public Rectangle GetOpaqueBoundsInPixels(float scale, float dpi)
```

| Parameter | Typ | Beschreibung |
| --- | --- | --- |
| scale | Single | Der Zoomfaktor (1,0 entspricht 100 %). |
| dpi | Single | Die Auflösung, die von Punkten in Pixel (Dots per Inch) konvertiert werden soll. |

### Rückgabewert

Das undurchsichtige Rechteck der Form in Pixel.

### Bemerkungen

Diese Methode konvertiert[`OpaqueBoundsInPoints`](../opaqueboundsinpoints/) in ein Rechteck in Pixel und es ist nützlich , wenn Sie eine Bitmap zum Rendern der Form mit nur einem undurchsichtigen Teil der Form erstellen möchten.

### Beispiele

Zeigt, wie Formen gemessen und skaliert werden.

```csharp
Document doc = new Document(MyDir + "Office math.docx");

OfficeMath officeMath = (OfficeMath)doc.GetChild(NodeType.OfficeMath, 0, true);
OfficeMathRenderer renderer = new OfficeMathRenderer(officeMath);

// Überprüfen Sie die Größe des Bildes, das das OfficeMath-Objekt beim Rendern erstellt.
Assert.AreEqual(119.0f, renderer.SizeInPoints.Width, 0.2f);
Assert.AreEqual(13.0f, renderer.SizeInPoints.Height, 0.1f);

Assert.AreEqual(119.0f, renderer.BoundsInPoints.Width, 0.2f);
Assert.AreEqual(13.0f, renderer.BoundsInPoints.Height, 0.1f);

// Shapes mit transparenten Teilen können unterschiedliche Werte in den "OpaqueBoundsInPoints"-Eigenschaften enthalten.
Assert.AreEqual(119.0f, renderer.OpaqueBoundsInPoints.Width, 0.2f);
Assert.AreEqual(14.2f, renderer.OpaqueBoundsInPoints.Height, 0.1f);

// Holen Sie sich die Formgröße in Pixel, mit linearer Skalierung auf eine bestimmte DPI.
Rectangle bounds = renderer.GetBoundsInPixels(1.0f, 96.0f);

Assert.AreEqual(159, bounds.Width);
Assert.AreEqual(18, bounds.Height);

// Holen Sie sich die Formgröße in Pixel, aber mit einem anderen DPI für die horizontalen und vertikalen Dimensionen.
bounds = renderer.GetBoundsInPixels(1.0f, 96.0f, 150.0f);
Assert.AreEqual(159, bounds.Width);
Assert.AreEqual(28, bounds.Height);

// Die undurchsichtigen Grenzen können auch hier variieren.
bounds = renderer.GetOpaqueBoundsInPixels(1.0f, 96.0f);

Assert.AreEqual(159, bounds.Width);
Assert.AreEqual(18, bounds.Height);

bounds = renderer.GetOpaqueBoundsInPixels(1.0f, 96.0f, 150.0f);

Assert.AreEqual(159, bounds.Width);
Assert.AreEqual(30, bounds.Height);
```

### Siehe auch

* class [NodeRendererBase](../)
* namensraum [Aspose.Words.Rendering](../../noderendererbase/)
* Montage [Aspose.Words](../../../)

---

## GetOpaqueBoundsInPixels(float, float, float) {#getopaqueboundsinpixels_1}

Berechnet die undurchsichtigen Grenzen der Form in Pixeln für einen angegebenen Zoomfaktor und eine angegebene Auflösung.

```csharp
public Rectangle GetOpaqueBoundsInPixels(float scale, float horizontalDpi, float verticalDpi)
```

| Parameter | Typ | Beschreibung |
| --- | --- | --- |
| scale | Single | Der Zoomfaktor (1,0 entspricht 100 %). |
| horizontalDpi | Single | Die horizontale Auflösung, die von Punkten in Pixel (Punkte pro Zoll) konvertiert werden soll. |
| verticalDpi | Single | Die vertikale Auflösung, die von Punkten in Pixel (Dots per Inch) konvertiert werden soll. |

### Rückgabewert

Das undurchsichtige Rechteck der Form in Pixel.

### Bemerkungen

Diese Methode konvertiert[`OpaqueBoundsInPoints`](../opaqueboundsinpoints/) in ein Rechteck in Pixel und es ist nützlich , wenn Sie eine Bitmap zum Rendern der Form mit nur einem undurchsichtigen Teil der Form erstellen möchten.

### Beispiele

Zeigt, wie Formen gemessen und skaliert werden.

```csharp
Document doc = new Document(MyDir + "Office math.docx");

OfficeMath officeMath = (OfficeMath)doc.GetChild(NodeType.OfficeMath, 0, true);
OfficeMathRenderer renderer = new OfficeMathRenderer(officeMath);

// Überprüfen Sie die Größe des Bildes, das das OfficeMath-Objekt beim Rendern erstellt.
Assert.AreEqual(119.0f, renderer.SizeInPoints.Width, 0.2f);
Assert.AreEqual(13.0f, renderer.SizeInPoints.Height, 0.1f);

Assert.AreEqual(119.0f, renderer.BoundsInPoints.Width, 0.2f);
Assert.AreEqual(13.0f, renderer.BoundsInPoints.Height, 0.1f);

// Shapes mit transparenten Teilen können unterschiedliche Werte in den "OpaqueBoundsInPoints"-Eigenschaften enthalten.
Assert.AreEqual(119.0f, renderer.OpaqueBoundsInPoints.Width, 0.2f);
Assert.AreEqual(14.2f, renderer.OpaqueBoundsInPoints.Height, 0.1f);

// Holen Sie sich die Formgröße in Pixel, mit linearer Skalierung auf eine bestimmte DPI.
Rectangle bounds = renderer.GetBoundsInPixels(1.0f, 96.0f);

Assert.AreEqual(159, bounds.Width);
Assert.AreEqual(18, bounds.Height);

// Holen Sie sich die Formgröße in Pixel, aber mit einem anderen DPI für die horizontalen und vertikalen Dimensionen.
bounds = renderer.GetBoundsInPixels(1.0f, 96.0f, 150.0f);
Assert.AreEqual(159, bounds.Width);
Assert.AreEqual(28, bounds.Height);

// Die undurchsichtigen Grenzen können auch hier variieren.
bounds = renderer.GetOpaqueBoundsInPixels(1.0f, 96.0f);

Assert.AreEqual(159, bounds.Width);
Assert.AreEqual(18, bounds.Height);

bounds = renderer.GetOpaqueBoundsInPixels(1.0f, 96.0f, 150.0f);

Assert.AreEqual(159, bounds.Width);
Assert.AreEqual(30, bounds.Height);
```

### Siehe auch

* class [NodeRendererBase](../)
* namensraum [Aspose.Words.Rendering](../../noderendererbase/)
* Montage [Aspose.Words](../../../)


