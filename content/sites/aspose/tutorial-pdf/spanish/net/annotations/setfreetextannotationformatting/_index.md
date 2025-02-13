---
title: Establecer formato de anotación de texto libre
linktitle: Establecer formato de anotación de texto libre
second_title: Referencia de API de Aspose.PDF para .NET
description: Este artículo proporciona una guía paso a paso sobre cómo crear una anotación de texto libre y especificar su contenido usando Aspose.PDF para .NET
type: docs
weight: 140
url: /es/net/annotations/setfreetextannotationformatting/
---

Aspose.PDF para .NET es una API de manipulación de documentos PDF potente y fácil de usar que le permite trabajar con archivos PDF mediante programación en sus aplicaciones .NET. Una de las características proporcionadas por Aspose.PDF para .NET es la capacidad de configurar el formato de anotación de texto libre en documentos PDF. En este artículo, lo guiaremos a través del proceso paso a paso para configurar el formato de anotación de texto libre usando Aspose.PDF para .NET.

## requisitos previos

Antes de comenzar, asegúrese de tener los siguientes requisitos previos:

- Microsoft Visual Studio 2010 o posterior
- Aspose.PDF para .NET
- Conocimientos básicos de C#



## 1. Cree una nueva aplicación de consola C#

Primero, cree una nueva aplicación de consola C# en Microsoft Visual Studio. Para crear una nueva aplicación de consola, seleccione "Archivo" > "Nuevo" > "Proyecto" > "Visual C#" > "Aplicación de consola" en el menú principal.

## 2. Agregar referencia a Aspose.PDF para .NET

continuación, agregue una referencia a Aspose.PDF para .NET en su proyecto. Para hacer esto, haga clic con el botón derecho en su proyecto en el panel "Explorador de soluciones", seleccione "Agregar" > "Referencia" y luego busque la ubicación donde guardó el archivo Aspose.PDF para .NET DLL. Seleccione el archivo DLL y haga clic en "Aceptar" para agregar la referencia a su proyecto.

## 3. Configurar el entorno

Después de agregar la referencia a Aspose.PDF para .NET, debe configurar el entorno. Para hacer esto, cree una nueva variable de cadena llamada "dataDir" y configúrela en la ruta del directorio donde se encuentra su documento PDF. Reemplace "SU DIRECTORIO DE DOCUMENTOS" en el código a continuación con la ruta real de su directorio de documentos:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 4. Abra el documento PDF

Una vez que haya configurado el entorno, puede abrir el documento PDF utilizando el siguiente código:

```csharp
// Abrir documento
Document pdfDocument = new Document(dataDir + "SetFreeTextAnnotationFormatting.pdf");
```

Reemplace "SetFreeTextAnnotationFormatting.pdf" con el nombre real de su documento PDF.

## 5. Configurar la apariencia predeterminada

Para configurar la apariencia predeterminada de la anotación de texto libre, debe crear una instancia del objeto DefaultAppearance con la fuente, el tamaño de fuente y el color deseados. En este tutorial, estamos configurando la fuente en "Arial", el tamaño de fuente en 28 y el color en rojo.

```csharp
// Crear una instancia del objeto DefaultAppearance
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 28, System.Drawing.Color.Red);
```

## 6. Crea una anotación de texto libre

Ahora que ha configurado la apariencia predeterminada, puede crear una anotación de texto libre con el siguiente código:

```csharp
// Crear anotación
FreeTextAnnotation freetext = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600), default_appearance);
```

El código anterior crea una nueva anotación de texto libre en la segunda página del documento PDF. La anotación se colocará en (200, 400) y tendrá un ancho de 400 y una altura de 600.

## 7. Especificar el contenido de la anotación

Después de crear la anotación de texto libre, puede especificar el contenido de la anotación mediante el siguiente código:

```csharp
// Especificar el contenido de la anotación
freetext.Contents = "Free Text
```

### Ejemplo de código fuente para Establecer formato de anotación de texto libre usando Aspose.PDF para .NET
```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	
	// Abrir documento
	Document pdfDocument = new Document(dataDir + "SetFreeTextAnnotationFormatting.pdf");

	// Crear una instancia del objeto DefaultAppearance
	DefaultAppearance default_appearance = new DefaultAppearance("Arial", 28, System.Drawing.Color.Red);
	// Crear anotación
	FreeTextAnnotation freetext = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600), default_appearance);
	// Especificar el contenido de la anotación
	freetext.Contents = "Free Text";
	// Agregar anotación a la colección de anotaciones de la página
	pdfDocument.Pages[1].Annotations.Add(freetext);
	dataDir = dataDir + "SetFreeTextAnnotationFormatting_out.pdf";
	//Guardar el documento actualizado
	pdfDocument.Save(dataDir);            
 
```
