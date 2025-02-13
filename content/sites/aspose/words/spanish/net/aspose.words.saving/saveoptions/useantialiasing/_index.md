---
title: SaveOptions.UseAntiAliasing
second_title: Referencia de API de Aspose.Words para .NET
description: SaveOptions propiedad. Obtiene o establece un valor que determina si se usa o no suavizado para renderizar.
type: docs
weight: 210
url: /es/net/aspose.words.saving/saveoptions/useantialiasing/
---
## SaveOptions.UseAntiAliasing property

Obtiene o establece un valor que determina si se usa o no suavizado para renderizar.

```csharp
public bool UseAntiAliasing { get; set; }
```

### Observaciones

El valor predeterminado es`falso` . Cuando este valor se establece en`verdadero` el suavizado se usa para renderizar.

Esta propiedad se utiliza cuando el documento se exporta a los siguientes formatos: Tiff ,Png ,Bmp , Jpeg ,Emf . Cuando el documento se exporta al Html ,Mhtml yEpub Formatos esta opción se usa para imágenes rasterizadas.

### Ejemplos

Muestra cómo mejorar la calidad de un documento renderizado con SaveOptions.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Size = 60;
builder.Writeln("Some text.");

SaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);

doc.Save(ArtifactsDir + "Document.ImageSaveOptions.Default.jpg", options);

options.UseAntiAliasing = true;
options.UseHighQualityRendering = true;

doc.Save(ArtifactsDir + "Document.ImageSaveOptions.HighQuality.jpg", options);
```

### Ver también

* class [SaveOptions](../)
* espacio de nombres [Aspose.Words.Saving](../../saveoptions/)
* asamblea [Aspose.Words](../../../)


