---
title: ImageSaveOptions.UseGdiEmfRenderer
second_title: Referencia de API de Aspose.Words para .NET
description: ImageSaveOptions propiedad. Obtiene o establece un valor que determina si usar GDI o el procesador de metarchivos Aspose.Words al guardar en EMF.
type: docs
weight: 180
url: /es/net/aspose.words.saving/imagesaveoptions/usegdiemfrenderer/
---
## ImageSaveOptions.UseGdiEmfRenderer property

Obtiene o establece un valor que determina si usar GDI+ o el procesador de metarchivos Aspose.Words al guardar en EMF.

```csharp
public bool UseGdiEmfRenderer { get; set; }
```

### Observaciones

Si se establece en`verdadero`Se utiliza el renderizador de metarchivos GDI+. Es decir, el contenido se escribe en el objeto graphics de GDI+ y se guarda en un metarchivo.

Si se establece en`falso` Se utiliza el renderizador de metarchivos Aspose.Words. Es decir, el contenido se escribe directamente en el formato de metarchivo con Aspose.Words.

Solo tiene efecto cuando se guarda en EMF.

El guardado de GDI+ solo funciona en .NET.

El valor predeterminado es`verdadero`.

### Ejemplos

Muestra cómo elegir un renderizador al convertir un documento a .emf.

```csharp
Document doc = new Document();
            DocumentBuilder builder = new DocumentBuilder(doc);

            builder.ParagraphFormat.Style = doc.Styles["Heading 1"];
            builder.Writeln("Hello world!");
            builder.InsertImage(ImageDir + "Logo.jpg");

            // Cuando guardamos el documento como una imagen EMF, podemos pasar un objeto SaveOptions para seleccionar un renderizador para la imagen.
            // Si establecemos el indicador "UseGdiEmfRenderer" en "true", Aspose.Words utilizará el renderizador GDI+.
            // Si establecemos el indicador "UseGdiEmfRenderer" en "falso", Aspose.Words utilizará su propio procesador de metarchivos.
            ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Emf);
            saveOptions.UseGdiEmfRenderer = useGdiEmfRenderer;

            doc.Save(ArtifactsDir + "ImageSaveOptions.Renderer.emf", saveOptions);

            // El renderizador GDI+ generalmente crea archivos más grandes.
            if (useGdiEmfRenderer)
#if NET48 || JAVA
                Assert.That(300000, Is.LessThan(new FileInfo(ArtifactsDir + "ImageSaveOptions.Renderer.emf").Length));
#elif NET5_0_OR_GREATER
                Assert.That(30000, Is.AtLeast(new FileInfo(ArtifactsDir + "ImageSaveOptions.Renderer.emf").Length));
#endif
            else
                Assert.That(30000, Is.AtLeast(new FileInfo(ArtifactsDir + "ImageSaveOptions.Renderer.emf").Length));
```

### Ver también

* class [ImageSaveOptions](../)
* espacio de nombres [Aspose.Words.Saving](../../imagesaveoptions/)
* asamblea [Aspose.Words](../../../)


