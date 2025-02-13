---
title: Formato 1Bpp indexado
linktitle: Formato 1Bpp indexado
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a formatear imágenes en 1 bpp indexadas con Aspose.Words para .NET. Tutorial completo para imágenes con poca profundidad de color.
type: docs
weight: 10
url: /es/net/programming-with-imagesaveoptions/format-1bpp-indexed/
---
En este tutorial, exploraremos el código fuente de C# proporcionado para la funcionalidad "Formato 1Bpp indexado" con Aspose.Words para .NET. Esta función le permite formatear imágenes en un documento en formato PNG con una profundidad de color de 1 bit por píxel (1 bpp) y un modo de color indexado.

## Paso 1: Configuración del entorno

Antes de comenzar, asegúrese de haber configurado su entorno de desarrollo con Aspose.Words para .NET. Asegúrese de haber agregado las referencias necesarias e importado los espacios de nombres apropiados.

## Paso 2: Cargar el documento

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 En este paso, cargamos el documento usando el`Document` método y pasando la ruta al archivo DOCX para cargar.

## Paso 3: Configure las opciones de copia de seguridad de imágenes

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(1),
     ImageColorMode = ImageColorMode.BlackAndWhite,
     PixelFormat = ImagePixelFormat.Format1bppIndexed
};
```

 En este paso, configuramos las opciones de respaldo para las imágenes. Creamos un nuevo`ImageSaveOptions`objeto especificando el formato de guardado deseado, aquí "Png" para el formato PNG. También definimos la página a incluir en la imagen, el modo de color blanco y negro y el formato de píxel indexado de 1 bpp.

## Paso 4: Copia de seguridad de las imágenes

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
```

 En este último paso, guardamos las imágenes del documento en formato PNG usando el`Save` y pasando la ruta al archivo de salida, junto con las opciones de guardado especificadas.

Ahora puede ejecutar el código fuente para formatear las imágenes del documento en formato PNG con una profundidad de color de 1 bpp indexado. El archivo resultante se guardará en el directorio especificado con el nombre "WorkingWithImageSaveOptions.Format1BppIndexed.Png".

### Ejemplo de código fuente para formato 1Bpp indexado usando Aspose.Words para .NET

```csharp 
 
			 //Ruta a su directorio de documentos
			 string dataDir = "YOUR DOCUMENT DIRECTORY"; 
            
            Document doc = new Document(dataDir + "Rendering.docx");

            ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
            {
                PageSet = new PageSet(1),
                ImageColorMode = ImageColorMode.BlackAndWhite,
                PixelFormat = ImagePixelFormat.Format1bppIndexed
            };

            doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
            
        
```

### Conclusión

En este tutorial, exploramos la función de formato indexado 1Bpp con Aspose.Words para .NET. Aprendimos a formatear imágenes en un documento en formato PNG con una profundidad de color de 1 bit por píxel (1 bpp) y un modo de color indexado.

Esta característica es útil cuando desea obtener imágenes con poca profundidad de color y tamaño de archivo pequeño. El formato indexado de 1Bpp permite que las imágenes se representen mediante una paleta de colores indexada, lo que puede ser beneficioso para algunas aplicaciones específicas.

Aspose.Words para .NET ofrece una amplia gama de funciones avanzadas para la manipulación y generación de documentos. El formato indexado 1Bpp es una de las muchas herramientas poderosas que pone a tu disposición.