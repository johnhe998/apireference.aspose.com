---
title: Copiar hojas de trabajo de Excel entre libros de trabajo
linktitle: Copiar hojas de trabajo de Excel entre libros de trabajo
second_title: Referencia de API de Aspose.Cells para .NET
description: Copie fácilmente hojas de trabajo entre libros de Excel usando Aspose.Cells para .NET.
type: docs
weight: 30
url: /es/net/excel-copy-worksheet/excel-copy-worksheets-between-workbooks/
---
En este tutorial, lo guiaremos a través de los pasos para copiar hojas de trabajo entre libros de Excel usando la biblioteca Aspose.Cells para .NET. Siga las instrucciones a continuación para completar esta tarea.

## Paso 1: Preparación

Asegúrese de haber instalado Aspose.Cells para .NET y creado un proyecto C# en su entorno de desarrollo integrado (IDE) preferido.

## Paso 2: establezca la ruta del directorio del documento

 declarar un`dataDir` variable e inicialícelo con la ruta a su directorio de documentos. Por ejemplo :

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

 Asegúrese de reemplazar`"YOUR_DOCUMENTS_DIRECTORY"` con la ruta real a su directorio.

## Paso 3: Defina la ruta del archivo de entrada

 declarar un`InputPath` variable e inicialícelo con la ruta completa del archivo de Excel desde el que desea copiar la hoja de cálculo. Por ejemplo :

```csharp
string InputPath = dataDir + "book1.xls";
```

 Asegúrate de tener el archivo de Excel`book1.xls` en su directorio de documentos o especifique el nombre de archivo y la ubicación correctos.

## Paso 4: Cree un primer libro de Excel

 Utilizar el`Workbook` clase de Aspose.Cells para crear un primer libro de Excel y abrir el archivo especificado:

```csharp
Workbook excelWorkbook0 = new Workbook(InputPath);
```

## Paso 5: Cree un segundo libro de Excel

Cree un segundo libro de Excel:

```csharp
Workbook excelWorkbook1 = new Workbook();
```

## Paso 6: copie la hoja de trabajo del primer libro de trabajo al segundo libro de trabajo

 Utilizar el`Copy`método para copiar la primera hoja de trabajo del primer libro de trabajo al segundo libro de trabajo:

```csharp
excelWorkbook1.Worksheets[0].Copy(excelWorkbook0.Worksheets[0]);
```

## Paso 7: Guarde el archivo de Excel

Guarde el archivo de Excel que contiene la hoja de cálculo copiada:

```csharp
excelWorkbook1.Save(dataDir + "Copy WorksheetsBetweenWorkbooks_out.xls");
```

Asegúrese de especificar la ruta y el nombre de archivo deseados para el archivo de salida.

### Ejemplo de código fuente para copiar hojas de trabajo de Excel entre libros de trabajo usando Aspose.Cells para .NET 
```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string InputPath = dataDir + "book1.xls";
// Crear un libro de trabajo.
// Abra un archivo en el primer libro.
Workbook excelWorkbook0 = new Workbook(InputPath);
// Cree otro libro de trabajo.
Workbook excelWorkbook1 = new Workbook();
// Copie la primera hoja del primer libro en el segundo libro.
excelWorkbook1.Worksheets[0].Copy(excelWorkbook0.Worksheets[0]);
// Guarda el archivo.
excelWorkbook1.Save(dataDir + "CopyWorksheetsBetweenWorkbooks_out.xls");
```

## Conclusión

¡Felicidades! Ahora ha aprendido a copiar hojas de cálculo entre libros de Excel utilizando Aspose.Cells para .NET. Siéntase libre de usar este método en sus propios proyectos para manipular eficientemente los archivos de Excel.

### preguntas frecuentes

#### P. ¿Qué bibliotecas se necesitan para usar Aspose.Cells para .NET?

A. Para usar Aspose.Cells para .NET, debe incluir la biblioteca Aspose.Cells en su proyecto. Asegúrese de haber hecho referencia a esta biblioteca correctamente en su entorno de desarrollo integrado (IDE).

#### P. ¿Aspose.Cells es compatible con otros formatos de archivo de Excel, como XLSX?

A. Sí, Aspose.Cells admite varios formatos de archivo de Excel, incluidos XLSX, XLS, CSV, HTML y muchos más. Puede manipular estos formatos de archivo utilizando las funciones de Aspose.Cells para .NET.

#### P. ¿Puedo personalizar las opciones de diseño al copiar la hoja de cálculo?

A.  Sí, puede personalizar las opciones de configuración de la página al copiar la hoja de cálculo utilizando las propiedades de la`PageSetup` objeto. Puede especificar encabezados de página, pies de página, márgenes, orientaciones, etc.