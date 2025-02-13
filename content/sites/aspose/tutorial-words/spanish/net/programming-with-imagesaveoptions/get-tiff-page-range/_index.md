---
title: Obtener intervalo de páginas Tiff
linktitle: Obtener intervalo de páginas Tiff
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a extraer un rango de páginas TIFF con Aspose.Words para .NET. Tutorial completo para archivos TIFF personalizados.
type: docs
weight: 10
url: /es/net/programming-with-imagesaveoptions/get-tiff-page-range/
---

En este tutorial, exploraremos el código fuente de C# provisto para obtener un rango de páginas TIFF con Aspose.Words para .NET. Esta característica le permite extraer un rango específico de páginas de un documento y guardarlas como un archivo TIFF.

## Paso 1: Configuración del entorno

Antes de comenzar, asegúrese de haber configurado su entorno de desarrollo con Aspose.Words para .NET. Asegúrese de haber agregado las referencias necesarias e importado los espacios de nombres apropiados.

## Paso 2: Cargar el documento

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 En este paso, cargamos el documento usando el`Document` método y pasando la ruta al archivo DOCX para cargar.

## Paso 3: Guardar el documento completo en TIFF

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.MultipageTiff.tiff");
```

 En este paso, guardamos el documento completo en formato TIFF usando el`Save` método y especificando la ruta al archivo de salida con la extensión`.tiff`.

## Paso 4: Configure las opciones de respaldo para el rango de páginas

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
PageSet = new PageSet(new PageRange(0, 1)),
TiffCompression = TiffCompression.Ccitt4,
Resolution = 160
};
```

 En este paso, configuramos las opciones de copia de seguridad para el rango de páginas específico. Creamos un nuevo`ImageSaveOptions` objeto especificando el formato de guardado deseado, aquí "Tiff" para el formato TIFF. Usamos`PageSet` para especificar el rango de páginas que queremos extraer, aquí desde la página 0 hasta la página 1 (inclusive). También configuramos la compresión TIFF a`Ccitt4` y la resolución a 160 dpi.

## Paso 5: Guardar el rango de páginas en TIFF

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetTiffPageRange.tiff", saveOptions);
```

 En este último paso, guardamos el rango de páginas especificado en formato TIFF usando el`Save` pasando la ruta al archivo de salida con`.tiff` extensión, junto con las opciones de guardado especificadas.

Ahora puede ejecutar el código fuente para obtener un rango específico de páginas de su documento y guardarlas como un archivo TIFF. Los archivos resultantes se guardarán en el directorio especificado con los nombres "WorkingWithImageSaveOptions.MultipageTiff.tiff" para el documento completo y "WorkingWithImageSaveOptions.GetTiffPageRange.tiff" para el intervalo de páginas especificado.

### Ejemplo de código fuente de Obtener rango de páginas Tiff usando Aspose.Words para .NET

```csharp 

// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Rendering.docx");

doc.Save(dataDir + "WorkingWithImageSaveOptions.MultipageTiff.tiff");



ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
	PageSet = new PageSet(new PageRange(0, 1)), TiffCompression = TiffCompression.Ccitt4, Resolution = 160
};

doc.Save(dataDir + "WorkingWithImageSaveOptions.GetTiffPageRange.tiff", saveOptions);
            
            
        
```

## Conclusión

En este tutorial, exploramos la funcionalidad de obtener un rango de páginas TIFF con Aspose.Words para .NET. Aprendimos cómo extraer un rango específico de páginas de un documento y guardarlas como un archivo TIFF.

Esta característica es útil cuando desea extraer solo ciertas páginas de un documento y guardarlas en un formato de imagen estándar como TIFF. También puede personalizar las opciones de compresión y resolución para obtener archivos TIFF de la mejor calidad.

Aspose.Words para .NET ofrece una amplia gama de funciones avanzadas para la manipulación y generación de documentos. Obtener un rango de páginas TIFF es una de las muchas herramientas poderosas que pone a su disposición.

Siéntase libre de integrar esta funcionalidad en sus proyectos Aspose.Words para .NET para extraer y guardar rangos específicos de páginas de sus documentos en formato TIFF.