---
title: ImageSaveOptions.PixelFormat
second_title: Referencia de API de Aspose.Words para .NET
description: ImageSaveOptions propiedad. Obtiene o establece el formato de píxeles de las imágenes generadas.
type: docs
weight: 110
url: /es/net/aspose.words.saving/imagesaveoptions/pixelformat/
---
## ImageSaveOptions.PixelFormat property

Obtiene o establece el formato de píxeles de las imágenes generadas.

```csharp
public ImagePixelFormat PixelFormat { get; set; }
```

### Observaciones

Esta propiedad solo tiene efecto cuando se guarda en formatos de imagen ráster.

El valor predeterminado esFormat32BppArgb.

El formato de píxeles de la imagen de salida puede diferir del valor establecido debido al trabajo de GDI+.

### Ejemplos

Muestra cómo seleccionar una tasa de bits por píxel con la que convertir un documento en una imagen.

```csharp
Document doc = new Document();
            DocumentBuilder builder = new DocumentBuilder(doc);

            builder.ParagraphFormat.Style = doc.Styles["Heading 1"];
            builder.Writeln("Hello world!");
            builder.InsertImage(ImageDir + "Logo.jpg");

            Assert.That(20000, Is.LessThan(new FileInfo(ImageDir + "Logo.jpg").Length));

            // Cuando guardamos el documento como una imagen, podemos pasar un objeto SaveOptions a
            // seleccione un formato de píxel para la imagen que generará la operación de guardado.
            // Varias tasas de bits por píxel afectarán la calidad y el tamaño del archivo de la imagen generada.
            ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png);
            imageSaveOptions.PixelFormat = imagePixelFormat;

            // Podemos clonar instancias de ImageSaveOptions.
            Assert.AreNotEqual(imageSaveOptions, imageSaveOptions.Clone());

            doc.Save(ArtifactsDir + "ImageSaveOptions.PixelFormat.png", imageSaveOptions);

#if NET48 || JAVA
            switch (imagePixelFormat)
            {
                case ImagePixelFormat.Format1bppIndexed:
                    Assert.That(10000, Is.AtLeast(new FileInfo(ArtifactsDir + "ImageSaveOptions.PixelFormat.png").Length));
                    break;
                case ImagePixelFormat.Format16BppRgb555:
                    Assert.That(80000, Is.LessThan(new FileInfo(ArtifactsDir + "ImageSaveOptions.PixelFormat.png").Length));
                    break;
                case ImagePixelFormat.Format24BppRgb:
                    Assert.That(125000, Is.LessThan(new FileInfo(ArtifactsDir + "ImageSaveOptions.PixelFormat.png").Length));
                    break;
                case ImagePixelFormat.Format32BppRgb:
                    Assert.That(150000, Is.LessThan(new FileInfo(ArtifactsDir + "ImageSaveOptions.PixelFormat.png").Length));
                    break;
                case ImagePixelFormat.Format48BppRgb:
                    Assert.That(200000, Is.LessThan(new FileInfo(ArtifactsDir + "ImageSaveOptions.PixelFormat.png").Length));
                    break;
            }
#elif NET5_0_OR_GREATER
            switch (imagePixelFormat)
            {
                case ImagePixelFormat.Format1bppIndexed:
                    Assert.That(10000, Is.AtLeast(new FileInfo(ArtifactsDir + "ImageSaveOptions.PixelFormat.png").Length));
                    break;
                case ImagePixelFormat.Format24BppRgb:
                    Assert.That(70000, Is.LessThan(new FileInfo(ArtifactsDir + "ImageSaveOptions.PixelFormat.png").Length));
                    break;
                case ImagePixelFormat.Format16BppRgb555:
                case ImagePixelFormat.Format32BppRgb:
                case ImagePixelFormat.Format48BppRgb:
                    Assert.That(125000, Is.LessThan(new FileInfo(ArtifactsDir + "ImageSaveOptions.PixelFormat.png").Length));
                    break;
            }
#endif
```

### Ver también

* enum [ImagePixelFormat](../../imagepixelformat/)
* class [ImageSaveOptions](../)
* espacio de nombres [Aspose.Words.Saving](../../imagesaveoptions/)
* asamblea [Aspose.Words](../../../)


