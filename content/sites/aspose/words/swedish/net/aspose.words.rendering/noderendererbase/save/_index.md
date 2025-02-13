---
title: NodeRendererBase.Save
second_title: Aspose.Words för .NET API Referens
description: NodeRendererBase metod. Gör formen till en bild och sparar den i en fil.
type: docs
weight: 90
url: /sv/net/aspose.words.rendering/noderendererbase/save/
---
## Save(string, ImageSaveOptions) {#save_1}

Gör formen till en bild och sparar den i en fil.

```csharp
public void Save(string fileName, ImageSaveOptions saveOptions)
```

| Parameter | Typ | Beskrivning |
| --- | --- | --- |
| fileName | String | Namnet på bildfilen. Om en fil med det angivna namnet redan finns, skrivs den befintliga filen över. |
| saveOptions | ImageSaveOptions | Anger alternativen som styr hur formen renderas och sparas. Kan vara null. |

### Exempel

Visar hur man renderar ett Office Math-objekt till en bildfil i det lokala filsystemet.

```csharp
Document doc = new Document(MyDir + "Office math.docx");

OfficeMath math = (OfficeMath)doc.GetChild(NodeType.OfficeMath, 0, true);

// Skapa ett "ImageSaveOptions"-objekt för att skicka till nodrenderarens "Save"-metod för att ändra
// hur det återger OfficeMath-noden till en bild.
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png);

// Ställ in egenskapen "Skala" till 5 för att återge objektet till fem gånger dess ursprungliga storlek.
saveOptions.Scale = 5;

math.GetMathRenderer().Save(ArtifactsDir + "Shape.RenderOfficeMath.png", saveOptions);
```

### Se även

* class [ImageSaveOptions](../../../aspose.words.saving/imagesaveoptions/)
* class [NodeRendererBase](../)
* namnutrymme [Aspose.Words.Rendering](../../noderendererbase/)
* hopsättning [Aspose.Words](../../../)

---

## Save(Stream, ImageSaveOptions) {#save}

Gör formen till en bild och sparar den i en ström.

```csharp
public void Save(Stream stream, ImageSaveOptions saveOptions)
```

| Parameter | Typ | Beskrivning |
| --- | --- | --- |
| stream | Stream | Strömmen där bilden av formen ska sparas. |
| saveOptions | ImageSaveOptions | Anger alternativen som styr hur formen renderas och sparas. Kan vara null. Om detta är null, kommer bilden att sparas i PNG-format. |

### Exempel

Visar hur man använder en formrenderare för att exportera former till filer i det lokala filsystemet.

```csharp
Document doc = new Document(MyDir + "Various shapes.docx");
Shape[] shapes = doc.GetChildNodes(NodeType.Shape, true).OfType<Shape>().ToArray();

Assert.AreEqual(7, shapes.Length);

// Det finns 7 former i dokumentet, inklusive en gruppform med 2 underordnade former.
// Vi kommer att rendera varje form till en bildfil i det lokala filsystemet
// medan man ignorerar gruppformerna eftersom de inte har något utseende.
// Detta kommer att producera 6 bildfiler.
foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true).OfType<Shape>())
{
    ShapeRenderer renderer = shape.GetShapeRenderer();
    ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Png);
    renderer.Save(ArtifactsDir + $"Shape.RenderAllShapes.{shape.Name}.png", options);
}
```

### Se även

* class [ImageSaveOptions](../../../aspose.words.saving/imagesaveoptions/)
* class [NodeRendererBase](../)
* namnutrymme [Aspose.Words.Rendering](../../noderendererbase/)
* hopsättning [Aspose.Words](../../../)


