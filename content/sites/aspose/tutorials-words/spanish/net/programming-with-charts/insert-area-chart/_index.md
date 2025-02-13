---
title: Insertar gráfico de área en un documento de Word
linktitle: Insertar gráfico de área en un documento de Word
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a insertar un gráfico de áreas en un documento con Aspose.Words para .NET. Agregue datos de serie y guarde el documento con el gráfico.
type: docs
weight: 10
url: /es/net/programming-with-charts/insert-area-chart/
---

Este tutorial explica cómo usar Aspose.Words para .NET para insertar un gráfico de área en un documento. El código fuente proporcionado demuestra cómo crear un gráfico, agregar datos de series y guardar el documento.

## Paso 1: configurar el proyecto

Asegúrese de tener los siguientes requisitos previos:

- Aspose.Words para la biblioteca .NET instalada. Puede descargarlo utilizando el administrador de paquetes NuGet para instalarlo.
- Una ruta de directorio del documento donde se guardará el documento de salida.

## Paso 2: Cree un nuevo documento e inserte un gráfico

 Crear un nuevo`Document` objeto y un`DocumentBuilder` para construir el documento.

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 A continuación, utilice el`InsertChart` metodo de la`DocumentBuilder` para insertar un gráfico de áreas en el documento.

```csharp
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## Paso 3: Agregar datos de series al gráfico

Agregue datos de serie al gráfico. En este ejemplo, agregaremos cinco puntos de datos con fechas y valores correspondientes.

```csharp
chart.Series.Add("Aspose Series 1", new []
{
    new DateTime(2002, 05, 01),
    new DateTime(2002, 06, 01),
    new DateTime(2002, 07, 01),
    new DateTime(2002, 08, 01),
    new DateTime(2002, 09, 01)
}, 
new double[] { 32, 32, 28, 12, 15 });
```

## Paso 4: Guarde el documento

 Finalmente, guarde el documento en el directorio especificado usando el`Save` metodo de la`Document` objeto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertAreaChart.docx");
```

Esto completa la implementación de insertar un gráfico de área usando Aspose.Words para .NET.

### Ejemplo de código fuente para Insertar gráfico de área usando Aspose.Words para .NET 

```csharp
	//Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new []
		{
			new DateTime(2002, 05, 01),
			new DateTime(2002, 06, 01),
			new DateTime(2002, 07, 01),
			new DateTime(2002, 08, 01),
			new DateTime(2002, 09, 01)
		}, 
		new double[] { 32, 32, 28, 12, 15 });
	doc.Save(dataDir + "WorkingWithCharts.InsertAreaChart.docx");
```

### Conclusión

En este tutorial, ha aprendido a insertar un gráfico de áreas en un documento de Word utilizando Aspose.Words para .NET. Siguiendo la guía paso a paso y utilizando el código fuente proporcionado, puede crear un nuevo documento, insertar un gráfico de área, agregar datos de serie y guardar el documento con el gráfico.

Aspose.Words para .NET proporciona una potente API para el procesamiento de textos con gráficos en documentos de Word. Con solo unas pocas líneas de código, puede crear gráficos de área de aspecto profesional y personalizarlos según sus requisitos. Los gráficos de área se usan comúnmente para mostrar la magnitud y las tendencias de los datos a lo largo del tiempo o las categorías.

Al usar Aspose.Words para .NET, puede automatizar el proceso de generación de documentos con gráficos de área, ahorrando tiempo y esfuerzo en la creación manual de documentos. La biblioteca ofrece una amplia gama de tipos de gráficos y opciones de personalización, lo que le permite crear gráficos visualmente atractivos e informativos en sus documentos de Word.

### preguntas frecuentes

#### Q1. ¿Qué es Aspose.Words para .NET?
Aspose.Words para .NET es una potente biblioteca de procesamiento de documentos que permite a los desarrolladores crear, modificar y convertir documentos de Word mediante programación en aplicaciones .NET. Proporciona un conjunto integral de API para el procesamiento de textos con elementos de documentos, incluidos gráficos, párrafos, tablas y más.

#### Q2. ¿Cómo instalo Aspose.Words para .NET?
Para instalar Aspose.Words para .NET, puede usar el administrador de paquetes NuGet en Visual Studio para instalar la biblioteca directamente en su proyecto. Simplemente busque "Aspose.Words" en el administrador de paquetes NuGet e instale el paquete.

#### Q3. ¿Puedo personalizar la apariencia del gráfico de áreas?
Sí, con Aspose.Words para .NET, puede personalizar varios aspectos de la apariencia del gráfico de áreas. Puede modificar propiedades como el título del gráfico, el color de la serie, las etiquetas de los ejes y el formato del área del gráfico. La biblioteca proporciona un amplio conjunto de API para controlar los elementos visuales del gráfico y crear una apariencia personalizada que se adapte a sus necesidades.

#### Q4. ¿Puedo agregar varias series al gráfico de áreas?
Sí, puede agregar varias series al gráfico de áreas mediante Aspose.Words para .NET. Cada serie representa un conjunto de puntos de datos que se trazan en el gráfico. Puede agregar series con diferentes conjuntos de datos y personalizar cada serie individualmente, incluido su nombre, puntos de datos y apariencia.

#### P5. ¿Puedo guardar el documento con el gráfico de áreas insertado en diferentes formatos?
 Sí, Aspose.Words para .NET le permite guardar el documento con el gráfico de área insertado en varios formatos, como DOCX, PDF, HTML y más. Puede elegir el formato de salida deseado en función de sus requisitos y utilizar el`Save` metodo de la`Document` objeto para guardar el documento. El gráfico de área insertado se conservará en el documento guardado.

#### P6. ¿Puedo modificar los datos y la apariencia del gráfico de áreas después de insertarlo?
Sí, después de insertar el gráfico de áreas en el documento, puede modificar sus datos y apariencia utilizando las API proporcionadas por Aspose.Words para .NET. Puede actualizar los datos de la serie, cambiar el tipo de gráfico, personalizar las propiedades de los ejes y aplicar opciones de formato para crear gráficos dinámicos e interactivos en sus documentos de Word.