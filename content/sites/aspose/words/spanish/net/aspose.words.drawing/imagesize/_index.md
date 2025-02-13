---
title: Class ImageSize
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Drawing.ImageSize clase. Contiene información sobre el tamaño y la resolución de la imagen.
type: docs
weight: 940
url: /es/net/aspose.words.drawing/imagesize/
---
## ImageSize class

Contiene información sobre el tamaño y la resolución de la imagen.

```csharp
public class ImageSize
```

## Constructores

| Nombre | Descripción |
| --- | --- |
| [ImageSize](imagesize/#constructor)(int, int) | Inicializa el ancho y el alto a los valores dados en píxeles. Inicializa la resolución a 96 ppp. |
| [ImageSize](imagesize/#constructor_1)(int, int, double, double) | Inicializa ancho, alto y resolución a los valores dados. |

## Propiedades

| Nombre | Descripción |
| --- | --- |
| [HeightPixels](../../aspose.words.drawing/imagesize/heightpixels/) { get; } | Obtiene la altura de la imagen en píxeles. |
| [HeightPoints](../../aspose.words.drawing/imagesize/heightpoints/) { get; } | Obtiene la altura de la imagen en puntos. 1 punto es 1/72 pulgadas. |
| [HorizontalResolution](../../aspose.words.drawing/imagesize/horizontalresolution/) { get; } | Obtiene la resolución horizontal en DPI. |
| [VerticalResolution](../../aspose.words.drawing/imagesize/verticalresolution/) { get; } | Obtiene la resolución vertical en DPI. |
| [WidthPixels](../../aspose.words.drawing/imagesize/widthpixels/) { get; } | Obtiene el ancho de la imagen en píxeles. |
| [WidthPoints](../../aspose.words.drawing/imagesize/widthpoints/) { get; } | Obtiene el ancho de la imagen en puntos. 1 punto es 1/72 pulgadas. |

### Ejemplos

Muestra cómo cambiar el tamaño de una forma con una imagen.

```csharp
#if NET48 || JAVA
            Image image = Image.FromFile(ImageDir + "Logo.jpg");

            Assert.AreEqual(400, image.Size.Width);
            Assert.AreEqual(400, image.Size.Height);
#elif NET5_0_OR_GREATER
            SKBitmap image = SKBitmap.Decode(ImageDir + "Logo.jpg");

            Assert.AreEqual(400, image.Width);
            Assert.AreEqual(400, image.Height);
#endif

            // Cuando insertamos una imagen usando el método "InsertImage", el constructor escala la forma que muestra la imagen para que,
            // cuando vemos el documento con un zoom del 100 % en Microsoft Word, la forma muestra la imagen en su tamaño real.
            Document doc = new Document();
            DocumentBuilder builder = new DocumentBuilder(doc);
            Shape shape = builder.InsertImage(ImageDir + "Logo.jpg");

            // Una imagen de 400x400 creará un objeto ImageData con un tamaño de imagen de 300x300pt.
            ImageSize imageSize = shape.ImageData.ImageSize;

            Assert.AreEqual(300.0d, imageSize.WidthPoints);
            Assert.AreEqual(300.0d, imageSize.HeightPoints);

            // Si las dimensiones de una forma coinciden con las dimensiones de los datos de la imagen,
            // entonces la forma muestra la imagen en su tamaño original.
            Assert.AreEqual(300.0d, shape.Width);
            Assert.AreEqual(300.0d, shape.Height);

              // Reducir el tamaño total de la forma en un 50%.
            shape.Width *= 0.5;

              // Los factores de escala se aplican tanto al ancho como a la altura al mismo tiempo para preservar las proporciones de la forma.
            Assert.AreEqual(150.0d, shape.Width);
            Assert.AreEqual(150.0d, shape.Height);

            // Cuando cambiamos el tamaño de la forma, el tamaño de los datos de la imagen sigue siendo el mismo.
            Assert.AreEqual(300.0d, imageSize.WidthPoints);
            Assert.AreEqual(300.0d, imageSize.HeightPoints);

            // Podemos hacer referencia a las dimensiones de los datos de la imagen para aplicar una escala basada en el tamaño de la imagen.
            shape.Width = imageSize.WidthPoints * 1.1;

            Assert.AreEqual(330.0d, shape.Width);
            Assert.AreEqual(330.0d, shape.Height);

            doc.Save(ArtifactsDir + "Image.ScaleImage.docx");
```

### Ver también

* property [ImageSize](../imagedata/imagesize/)
* espacio de nombres [Aspose.Words.Drawing](../../aspose.words.drawing/)
* asamblea [Aspose.Words](../../)


