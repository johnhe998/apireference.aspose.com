---
title: GraphicsQualityOptions.UseTileFlipMode
second_title: Aspose.Words per .NET API Reference
description: GraphicsQualityOptions proprietà. Ottiene o imposta un flag che indica se WrapMode è TileFlipXY.
type: docs
weight: 80
url: /it/net/aspose.words.saving/graphicsqualityoptions/usetileflipmode/
---
## GraphicsQualityOptions.UseTileFlipMode property

Ottiene o imposta un flag che indica se WrapMode è TileFlipXY.

```csharp
public bool UseTileFlipMode { get; set; }
```

### Osservazioni

IlWrapMode specifica come una trama o una sfumatura viene affiancata quando è più piccola dell'area da riempire.

Per impostazione predefinita utilizzaTile (specifica la piastrellatura senza capovolgere). Ciò causa un rendering impreciso dell'immagine in scala (con alta risoluzione).

Questa proprietà consente di passare da WrapMode aTileFlipXY (specifica che le tessere vengono capovolte orizzontalmente mentre ci si sposta lungo una riga e capovolte verticalmente mentre ci si sposta lungo una colonna).

### Esempi

Mostra come evitare che la linea bianca appaia durante il rendering ad alta risoluzione.

```csharp
Document doc = new Document(MyDir + "Shape high dpi.docx");

Shape shape = (Shape)doc.GetChild(NodeType.Shape, 0, true);
ShapeRenderer renderer = shape.GetShapeRenderer();

ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
{
    Resolution = 500, GraphicsQualityOptions = new GraphicsQualityOptions { UseTileFlipMode = true }
};
renderer.Save(ArtifactsDir + "ImageSaveOptions.UseTileFlipMode.png", saveOptions);
```

### Guarda anche

* class [GraphicsQualityOptions](../)
* spazio dei nomi [Aspose.Words.Saving](../../graphicsqualityoptions/)
* assemblea [Aspose.Words](../../../)


