---
title: OfficeMath.GetMathRenderer
second_title: Aspose.Words für .NET-API-Referenz
description: OfficeMath methode. Erstellt ein Objekt und gibt es zurück das verwendet werden kann um diese Gleichung in ein Bild zu rendern.
type: docs
weight: 80
url: /de/net/aspose.words.math/officemath/getmathrenderer/
---
## OfficeMath.GetMathRenderer method

Erstellt ein Objekt und gibt es zurück, das verwendet werden kann, um diese Gleichung in ein Bild zu rendern.

```csharp
public OfficeMathRenderer GetMathRenderer()
```

### Rückgabewert

Das Renderer-Objekt für diese Gleichung.

### Bemerkungen

Diese Methode ruft nur die auf[`OfficeMathRenderer`](../../../aspose.words.rendering/officemathrenderer/)Konstruktor und übergibt dieses Objekt als Parameter.

### Beispiele

Zeigt, wie ein Office Math-Objekt in eine Bilddatei im lokalen Dateisystem gerendert wird.

```csharp
Document doc = new Document(MyDir + "Office math.docx");

OfficeMath math = (OfficeMath)doc.GetChild(NodeType.OfficeMath, 0, true);

// Erstellen Sie ein "ImageSaveOptions"-Objekt, das an die "Save"-Methode des Node-Renderers übergeben wird, um es zu ändern
// wie es den OfficeMath-Knoten in ein Bild rendert.
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png);

// Setzen Sie die Eigenschaft "Scale" auf 5, um das Objekt auf das Fünffache seiner ursprünglichen Größe zu rendern.
saveOptions.Scale = 5;

math.GetMathRenderer().Save(ArtifactsDir + "Shape.RenderOfficeMath.png", saveOptions);
```

### Siehe auch

* class [OfficeMathRenderer](../../../aspose.words.rendering/officemathrenderer/)
* class [OfficeMath](../)
* namensraum [Aspose.Words.Math](../../officemath/)
* Montage [Aspose.Words](../../../)


