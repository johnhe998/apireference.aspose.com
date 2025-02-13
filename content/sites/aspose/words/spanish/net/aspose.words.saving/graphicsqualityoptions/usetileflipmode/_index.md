---
title: GraphicsQualityOptions.UseTileFlipMode
second_title: Referencia de API de Aspose.Words para .NET
description: GraphicsQualityOptions propiedad. Obtiene o establece un indicador que indica si WrapMode es TileFlipXY.
type: docs
weight: 80
url: /es/net/aspose.words.saving/graphicsqualityoptions/usetileflipmode/
---
## GraphicsQualityOptions.UseTileFlipMode property

Obtiene o establece un indicador que indica si WrapMode es TileFlipXY.

```csharp
public bool UseTileFlipMode { get; set; }
```

### Observaciones

losWrapMode especifica cómo se organiza una textura o un degradado cuando es más pequeño que el área que se está rellenando.

Por defecto utilizaTile (especifica mosaico sin voltear). Esto provoca una representación imprecisa de la imagen escalada (con alta resolución).

Esta propiedad permite cambiar WrapMode aTileFlipXY (especifica que los mosaicos se voltean horizontalmente a medida que avanza por una fila y verticalmente a medida que avanza por una columna).

### Ejemplos

Muestra cómo evitar que aparezca la línea blanca al renderizar con alta resolución.

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

### Ver también

* class [GraphicsQualityOptions](../)
* espacio de nombres [Aspose.Words.Saving](../../graphicsqualityoptions/)
* asamblea [Aspose.Words](../../../)


