---
title: NodeRendererBase.GetBoundsInPixels
second_title: Aspose.Words för .NET API Referens
description: NodeRendererBase metod. Beräknar formens gränser i pixlar för en angiven zoomfaktor och upplösning.
type: docs
weight: 40
url: /sv/net/aspose.words.rendering/noderendererbase/getboundsinpixels/
---
## GetBoundsInPixels(float, float) {#getboundsinpixels}

Beräknar formens gränser i pixlar för en angiven zoomfaktor och upplösning.

```csharp
public Rectangle GetBoundsInPixels(float scale, float dpi)
```

| Parameter | Typ | Beskrivning |
| --- | --- | --- |
| scale | Single | Zoomfaktorn (1,0 är 100%). |
| dpi | Single | Upplösningen (horisontell och vertikal) för att konvertera från punkter till pixlar (punkter per tum). |

### Returvärde

Den faktiska (som återges på sidan) begränsningsrutan för formen i pixlar.

### Anmärkningar

Denna metod konverterar[`BoundsInPoints`](../boundsinpoints/) till rektangel i pixlar.

### Exempel

Visar hur man mäter och skalar former.

```csharp
Document doc = new Document(MyDir + "Office math.docx");

OfficeMath officeMath = (OfficeMath)doc.GetChild(NodeType.OfficeMath, 0, true);
OfficeMathRenderer renderer = new OfficeMathRenderer(officeMath);

// Verifiera storleken på bilden som OfficeMath-objektet kommer att skapa när vi renderar den.
Assert.AreEqual(119.0f, renderer.SizeInPoints.Width, 0.2f);
Assert.AreEqual(13.0f, renderer.SizeInPoints.Height, 0.1f);

Assert.AreEqual(119.0f, renderer.BoundsInPoints.Width, 0.2f);
Assert.AreEqual(13.0f, renderer.BoundsInPoints.Height, 0.1f);

// Former med genomskinliga delar kan innehålla olika värden i egenskaperna "OpaqueBoundsInPoints".
Assert.AreEqual(119.0f, renderer.OpaqueBoundsInPoints.Width, 0.2f);
Assert.AreEqual(14.2f, renderer.OpaqueBoundsInPoints.Height, 0.1f);

// Få formstorleken i pixlar, med linjär skalning till en specifik DPI.
Rectangle bounds = renderer.GetBoundsInPixels(1.0f, 96.0f);

Assert.AreEqual(159, bounds.Width);
Assert.AreEqual(18, bounds.Height);

// Få formstorleken i pixlar, men med en annan DPI för de horisontella och vertikala dimensionerna.
bounds = renderer.GetBoundsInPixels(1.0f, 96.0f, 150.0f);
Assert.AreEqual(159, bounds.Width);
Assert.AreEqual(28, bounds.Height);

// De ogenomskinliga gränserna kan variera även här.
bounds = renderer.GetOpaqueBoundsInPixels(1.0f, 96.0f);

Assert.AreEqual(159, bounds.Width);
Assert.AreEqual(18, bounds.Height);

bounds = renderer.GetOpaqueBoundsInPixels(1.0f, 96.0f, 150.0f);

Assert.AreEqual(159, bounds.Width);
Assert.AreEqual(30, bounds.Height);
```

### Se även

* class [NodeRendererBase](../)
* namnutrymme [Aspose.Words.Rendering](../../noderendererbase/)
* hopsättning [Aspose.Words](../../../)

---

## GetBoundsInPixels(float, float, float) {#getboundsinpixels_1}

Beräknar formens gränser i pixlar för en angiven zoomfaktor och upplösning.

```csharp
public Rectangle GetBoundsInPixels(float scale, float horizontalDpi, float verticalDpi)
```

| Parameter | Typ | Beskrivning |
| --- | --- | --- |
| scale | Single | Zoomfaktorn (1,0 är 100%). |
| horizontalDpi | Single | Den horisontella upplösningen för att konvertera från punkter till pixlar (punkter per tum). |
| verticalDpi | Single | Den vertikala upplösningen för att konvertera från punkter till pixlar (punkter per tum). |

### Returvärde

Den faktiska (som återges på sidan) begränsningsrutan för formen i pixlar.

### Anmärkningar

Denna metod konverterar[`BoundsInPoints`](../boundsinpoints/) till rektangel i pixlar.

### Exempel

Visar hur man mäter och skalar former.

```csharp
Document doc = new Document(MyDir + "Office math.docx");

OfficeMath officeMath = (OfficeMath)doc.GetChild(NodeType.OfficeMath, 0, true);
OfficeMathRenderer renderer = new OfficeMathRenderer(officeMath);

// Verifiera storleken på bilden som OfficeMath-objektet kommer att skapa när vi renderar den.
Assert.AreEqual(119.0f, renderer.SizeInPoints.Width, 0.2f);
Assert.AreEqual(13.0f, renderer.SizeInPoints.Height, 0.1f);

Assert.AreEqual(119.0f, renderer.BoundsInPoints.Width, 0.2f);
Assert.AreEqual(13.0f, renderer.BoundsInPoints.Height, 0.1f);

// Former med genomskinliga delar kan innehålla olika värden i egenskaperna "OpaqueBoundsInPoints".
Assert.AreEqual(119.0f, renderer.OpaqueBoundsInPoints.Width, 0.2f);
Assert.AreEqual(14.2f, renderer.OpaqueBoundsInPoints.Height, 0.1f);

// Få formstorleken i pixlar, med linjär skalning till en specifik DPI.
Rectangle bounds = renderer.GetBoundsInPixels(1.0f, 96.0f);

Assert.AreEqual(159, bounds.Width);
Assert.AreEqual(18, bounds.Height);

// Få formstorleken i pixlar, men med en annan DPI för de horisontella och vertikala dimensionerna.
bounds = renderer.GetBoundsInPixels(1.0f, 96.0f, 150.0f);
Assert.AreEqual(159, bounds.Width);
Assert.AreEqual(28, bounds.Height);

// De ogenomskinliga gränserna kan variera även här.
bounds = renderer.GetOpaqueBoundsInPixels(1.0f, 96.0f);

Assert.AreEqual(159, bounds.Width);
Assert.AreEqual(18, bounds.Height);

bounds = renderer.GetOpaqueBoundsInPixels(1.0f, 96.0f, 150.0f);

Assert.AreEqual(159, bounds.Width);
Assert.AreEqual(30, bounds.Height);
```

### Se även

* class [NodeRendererBase](../)
* namnutrymme [Aspose.Words.Rendering](../../noderendererbase/)
* hopsättning [Aspose.Words](../../../)


